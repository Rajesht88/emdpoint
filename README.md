# emdpoint

# Define VPC Endpoint for Amazon Elastic Container Registry (ECR)

resource "aws_vpc_endpoint" "ecr_api" {
  vpc_id       = var.vpc_id
  service_name  = "com.amazonaws.ap-southeast-1.ecr.api"
  vpc_endpoint_type = "Interface"

  security_group_ids = [var.security_group_id]

  tags = {
    Name = "ecr-api-endpoint"
  }
}

resource "aws_vpc_endpoint" "ecr_dkr" {
  vpc_id       = var.vpc_id
  service_name  = "com.amazonaws.ap-southeast-1.ecr.dkr"
  vpc_endpoint_type = "Interface"

  security_group_ids = [var.security_group_id]

  tags = {
    Name = "ecr-dkr-endpoint"
  }
}

resource "aws_vpc_endpoint_gateway" "s3" {
  vpc_id       = var.vpc_id
  service_name  = "com.amazonaws.ap-southeast-1.s3"

  tags = {
    Name = "s3-endpoint"
  }
}

# Define VPC Endpoint for Application Load Balancers and Network Load Balancers

resource "aws_vpc_endpoint" "elb" {
  vpc_id       = var.vpc_id
  service_name  = "com.amazonaws.ap-southeast-1.elasticloadbalancing"
  vpc_endpoint_type = "Interface"

  security_group_ids = [var.security_group_id]

  tags = {
    Name = "elb-endpoint"
  }
}

# Define VPC Endpoint for AWS X-Ray

resource "aws_vpc_endpoint" "xray" {
  vpc_id       = var.vpc_id
  service_name  = "com.amazonaws.ap-southeast-1.xray"
  vpc_endpoint_type = "Interface"

  security_group_ids = [var.security_group_id]

  tags = {
    Name = "xray-endpoint"
  }
}

# Define VPC Endpoint for Amazon CloudWatch Logs

resource "aws_vpc_endpoint" "logs" {
  vpc_id       = var.vpc_id
  service_name  = "com.amazonaws.ap-southeast-1.logs"
  vpc_endpoint_type = "Interface"

  security_group_ids = [var.security_group_id]

  tags = {
    Name = "logs-endpoint"
  }
}

# Define VPC Endpoint for AWS Security Token Service (STS)

resource "aws_vpc_endpoint" "sts" {
  vpc_id       = var.vpc_id
  service_name  = "com.amazonaws.ap-southeast-1.sts"
  vpc_endpoint_type = "Interface"

  security_group_ids = [var.security_group_id]

  tags = {
    Name = "sts-endpoint"
  }
}
