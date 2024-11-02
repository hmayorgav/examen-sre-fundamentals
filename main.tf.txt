terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 4.0"
    }
  }

  required_version = ">= 1.0.0"
}

provider "aws" {
  region = "us-east-1"  # Change to your desired AWS region
}

resource "null_resource" "run_fibonacci" {
  provisioner "local-exec" {
    command = "python3 fibonacci.py"
  }
}
