# Installation Instructions for Python 3.13 Compatible Francinette

This version of francinette includes fixes for Python 3.13 compatibility (specifically, the `pipes` module has been replaced with `shlex`).

## Quick Install

To install from this repository, run:

```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/Prashant-Bharaj/francinette/master/install.sh)"
```

Or if you've cloned the repository locally:

```bash
cd francinette
bash install.sh
```

## What the Install Script Does

1. **Downloads the repository** from `https://github.com/Prashant-Bharaj/francinette.git`
2. **Installs system dependencies** (on Linux):
   - C compilers (gcc, clang)
   - Development libraries (libbsd-dev, libncurses-dev, etc.)
   - Python 3 and pip
3. **Creates a virtual environment** in `~/francinette/venv`
4. **Installs Python dependencies** from `requirements.txt`
5. **Sets up aliases** (`francinette` and `paco`) in your shell config file (`.bashrc` or `.zshrc`)

## Requirements

- Python 3.12 or higher (Python 3.13 compatible!)
- Git
- Bash shell
- On Linux: sudo access for installing system packages

## After Installation

1. **Reload your shell** or run:
   ```bash
   source ~/.bashrc  # or source ~/.zshrc if using zsh
   ```

2. **Test the installation**:
   ```bash
   francinette --help
   # or
   paco --help
   ```

3. **Use francinette** in your 42 project directories:
   ```bash
   cd ~/your-libft-project
   francinette
   ```

## Python 3.13 Compatibility

This version includes the following fixes for Python 3.13:
- Replaced `from pipes import quote` with `from shlex import quote` in:
  - `testers/libft/Fsoares.py`
  - `testers/pipex/Fsoares.py`
  - `testers/minitalk/Fsoares.py`

The `pipes` module was removed in Python 3.13, and `shlex.quote` is the recommended replacement.

## Troubleshooting

If you encounter issues:

1. **Python version**: Make sure you have Python 3.12+ installed:
   ```bash
   python3 --version
   ```

2. **Virtual environment**: If the venv creation fails, ensure `python3-venv` is installed:
   ```bash
   sudo apt install python3-venv  # Ubuntu/Debian
   ```

3. **Dependencies**: If pip install fails, try upgrading pip:
   ```bash
   pip3 install --upgrade pip
   ```

## Manual Installation (Alternative)

If the install script doesn't work, you can install manually:

```bash
cd ~
git clone --recursive https://github.com/Prashant-Bharaj/francinette.git
cd francinette
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

Then add to your `~/.bashrc` or `~/.zshrc`:
```bash
alias francinette="$HOME/francinette/tester.sh"
alias paco="$HOME/francinette/tester.sh"
```
