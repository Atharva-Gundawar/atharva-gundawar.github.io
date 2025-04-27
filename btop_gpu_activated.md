
# Compiling btop with NVIDIA GPU Support

## Prerequisites
- Git
- Build essentials (gcc, make)
- CUDA toolkit (for NVIDIA GPU support)

## Steps

1. Remove existing btop installation (if installed via snap):
   ```bash
   sudo snap remove btop
   ```

2. Clone the btop repository:
   ```bash
   mkdir -p ~/src
   cd ~/src
   git clone https://github.com/aristocratos/btop.git
   cd btop
   ```

3. Compile btop with GPU support:
   ```bash
   make GPU_SUPPORT=true -j$(nproc)
   ```

4. Install the compiled btop:
   ```bash
   sudo make install
   ```

5. Update PATH (if needed):
   ```bash
   echo 'export PATH="/usr/local/bin:$PATH"' >> ~/.bashrc
   source ~/.bashrc
   ```

6. Verify installation:
   ```bash
   btop --version
   ```
   Look for `Configured with: make ... GPU_SUPPORT=true` in the output.

7. Run btop to see your GPU metrics:
   ```bash
   btop
   ```
