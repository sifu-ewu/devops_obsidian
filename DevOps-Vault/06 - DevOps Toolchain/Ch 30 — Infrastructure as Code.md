---
aliases: [IaC, Infrastructure as Code, Terraform, Ansible]
tags: [part6, devops-tools, iac, terraform, ansible]
completed: false
chapter: 30
---

# 💡 Chapter 30 — Infrastructure as Code (IaC)

> [!info] **Part of** [[Part 6 — DevOps Toolchain]]

---

## 📖 What is IaC?

```
WITHOUT IaC (ClickOps): Console → click → undocumented, unreproducible
WITH IaC:              Code → git commit → apply → identical infra anywhere
```

---

## 📖 Terraform — The IaC Standard

```hcl
# main.tf
terraform {
  required_providers {
    aws = { source = "hashicorp/aws", version = "~> 5.0" }
  }
  backend "s3" {
    bucket = "my-terraform-state"
    key    = "production/terraform.tfstate"
    region = "us-east-1"
  }
}

provider "aws" { region = var.aws_region }

variable "aws_region" { default = "us-east-1" }
variable "instance_type" { default = "t3.medium" }

resource "aws_vpc" "main" {
  cidr_block           = "10.0.0.0/16"
  enable_dns_hostnames = true
  tags = { Name = "main-vpc", Environment = "production" }
}

resource "aws_subnet" "public" {
  vpc_id                  = aws_vpc.main.id
  cidr_block              = "10.0.1.0/24"
  map_public_ip_on_launch = true
}

resource "aws_security_group" "web" {
  name   = "web-sg"
  vpc_id = aws_vpc.main.id
  ingress { from_port=80; to_port=80; protocol="tcp"; cidr_blocks=["0.0.0.0/0"] }
  ingress { from_port=443; to_port=443; protocol="tcp"; cidr_blocks=["0.0.0.0/0"] }
  egress  { from_port=0; to_port=0; protocol="-1"; cidr_blocks=["0.0.0.0/0"] }
}

resource "aws_instance" "web" {
  ami                    = data.aws_ami.ubuntu.id
  instance_type          = var.instance_type
  subnet_id              = aws_subnet.public.id
  vpc_security_group_ids = [aws_security_group.web.id]
  tags = { Name = "web-server" }
}

output "public_ip" { value = aws_instance.web.public_ip }
```

```bash
terraform init      # Download providers
terraform plan      # Dry run — show changes
terraform apply     # Apply with confirmation
terraform destroy   # Tear down everything
```

---

## 📖 Ansible — Configuration Management

```yaml
# playbook.yml
---
- name: Configure Web Server
  hosts: webservers
  become: yes
  vars:
    app_dir: /var/www/myapp

  tasks:
    - name: Install packages
      apt:
        name: [nginx, python3, git]
        state: present
        update_cache: yes

    - name: Deploy from git
      git:
        repo: https://github.com/mycompany/myapp.git
        dest: "{{ app_dir }}"
        version: main
      notify: restart nginx

    - name: Ensure nginx running
      systemd: { name: nginx, enabled: yes, state: started }

  handlers:
    - name: restart nginx
      systemd: { name: nginx, state: reloaded }
```

> [!devops] **Terraform** provisions infrastructure (servers, networks). **Ansible** configures what's on the servers. They complement each other.

---

## Related

- [[Ch 27 — VPN Tunneling & Cloud Networking]] — VPC architecture
- [[Ch 29 — CI-CD Pipelines]] — IaC in pipeline stages
- [[Ch 21 — IP Addressing & Subnetting]] — Subnet CIDR blocks

---


- [ ] Mark as completed
> [!tip] 🧭 Navigation
> **← Prev** [[Ch 29 — CI-CD Pipelines]] | [[Part 6 — DevOps Toolchain]] | **Next →** [[Ch 31 — Monitoring & Observability]]
