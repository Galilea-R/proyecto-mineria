# Dockerfile
FROM python:3.11-slim

# Set environment variables
ENV DEBIAN_FRONTEND=noninteractive

# Install system dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    curl \
    git \
    sudo \
    openssh-client \
    && rm -rf /var/lib/apt/lists/*

# Create vscode user
RUN useradd -m vscode && echo "vscode ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

# Set user
USER vscode

# Install Jupyter and dependencies
RUN pip install --upgrade pip && \
    pip install jupyterlab kagglehub pandas numpy matplotlib scikit-learn ipykernel

# Expose port for Jupyter
EXPOSE 8888

# Start Jupyter Lab
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]