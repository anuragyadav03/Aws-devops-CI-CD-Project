#!/bin/bash

# Exit immediately if any command fails
set -e

echo "===== Updating system ====="
sudo apt update -y
sudo apt upgrade -y

echo "===== Installing required packages ====="
sudo apt install -y ruby wget curl

echo "===== Moving to ubuntu home directory ====="
cd /home/ubuntu

echo "===== Downloading CodeDeploy agent installer (us-east-1) ====="
wget https://aws-codedeploy-us-east-1.s3.us-east-1.amazonaws.com/latest/install

echo "===== Making installer executable ====="
chmod +x ./install

echo "===== Installing CodeDeploy agent ====="
sudo ./install auto

echo "===== Enabling CodeDeploy agent ====="
sudo systemctl enable codedeploy-agent

echo "===== Starting CodeDeploy agent ====="
sudo systemctl start codedeploy-agent

echo "===== Verifying CodeDeploy agent status ====="
sudo systemctl status codedeploy-agent --no-pager

echo "===== CodeDeploy agent installation completed successfully ====="
