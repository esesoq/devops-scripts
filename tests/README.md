#!/usr/bin/env python3

import os
import sys
import json
import subprocess

def get_version():
    with open('devops-scripts/version.txt', 'r') as f:
        return f.read().strip()

def get_dependencies():
    return subprocess.check_output(['pip', 'list', 'devops-scripts']).decode('utf-8').splitlines()

def get_dependencies_json():
    with open('devops-scripts/requirements.txt', 'r') as f:
        return f.read()

def main():
    print(f"Version: {get_version()}")
    print(f"Dependencies: {get_dependencies()}")
    print(f"Dependencies (JSON): {get_dependencies_json()}")
    print("")

if __name__ == "__main__":
    main()