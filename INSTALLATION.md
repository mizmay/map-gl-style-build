# Map GL Style Build - Installation Guide

This guide walks through installing and setting up `map-gl-style-build` in a new or existing project.

## Prerequisites

### Required Software
- **Node.js** (v16 or higher recommended)
- **npm** (comes bundled with Node.js)
- **Yarn** (package manager)

### Checking Current Installation

Before installing, verify what's already available on your system:

```bash
# Check Node.js version
node --version

# Check npm version (usually comes with Node.js)
npm --version

# Check Yarn version
yarn --version
```

### Installing Prerequisites (if needed)

#### Install Node.js
If Node.js is not installed or you need a newer version:

**Option 1: Download from official website**
- Visit [nodejs.org](https://nodejs.org/)
- Download the LTS version for your operating system
- Run the installer

**Option 2: Using a package manager**

**macOS (using Homebrew):**
```bash
brew install node
```

**Ubuntu/Debian:**
```bash
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs
```

**Windows (using Chocolatey):**
```bash
choco install nodejs
```

#### Install Yarn
If Yarn is not installed:

```bash
# Install Yarn globally using npm
npm install -g yarn

# Or install Yarn using the official installer
# Visit: https://yarnpkg.com/getting-started/install
```

## Installation Steps

### 1. Initialize Project (if needed)

If you're starting with a new project or one without package management:

```bash
# Initialize package.json
yarn init -y
```

This creates a `package.json` file with default values.

### 2. Install map-gl-style-build

```bash
# Install the latest version from GitHub
yarn add map-gl-style-build@https://github.com/mizmay/map-gl-style-build
```

### 3. Verify Installation

```bash
# Check version
yarn map-gl-style-build --version

# View help
yarn map-gl-style-build --help
```

Expected output:
```
0.9.0
```

## Project Structure

After installation, your project will have:

```
your-project/
├── package.json          # Project dependencies
├── yarn.lock            # Locked dependency versions
├── node_modules/        # Installed packages
└── .yarn/              # Yarn configuration
```

## Next Steps

### For Template-Based Projects

If you're using the tool to build styles from templates:

1. **Create template directories:**
   ```bash
   mkdir -p templates/styles templates/layers
   ```

2. **Add your style templates** to `templates/styles/`
3. **Add your layer templates** to `templates/layers/`
4. **Build your styles:**
   ```bash
   yarn map-gl-style-build --style-dir=templates/styles --layer-dir=templates/layers --out-dir=build
   ```

### For Converting Existing Styles

If you want to convert an existing style to templates:

1. **Use the create-layer-templates command:**
   ```bash
   yarn create-layer-templates --help
   ```

2. **Convert your existing style:**
   ```bash
   yarn create-layer-templates --in-dir=styles --out-dir=templates --base-style-path=styles/main-style.json
   ```

For more details see README.md

## Troubleshooting

### Common Issues

**"yarn: command not found"**
- Yarn is not installed or not in PATH
- Solution: Install Yarn using the steps above

**"node: command not found"**
- Node.js is not installed or not in PATH
- Solution: Install Node.js using the steps above

**Permission errors on macOS/Linux**
- Try using `sudo` for global installations
- Or use a Node version manager like `nvm`

**Version conflicts**
- Clear yarn cache: `yarn cache clean`
- Delete `node_modules` and `yarn.lock`, then reinstall

### Getting Help

- **Tool help:** `yarn map-gl-style-build --help`
- **Create templates help:** `yarn create-layer-templates --help`
- **GitHub repository:** [mizmay/map-gl-style-build](https://github.com/mizmay/map-gl-style-build)

## Example Usage

```bash
# Build a style with verbose output
yarn map-gl-style-build --style-dir=templates/styles --layer-dir=templates/layers --out-dir=build -v

# Create layer templates from existing style
yarn create-layer-templates --in-dir=styles --out-dir=templates --base-style-path=styles/main-style.json
```

---

*This guide was created based on the installation process for map-gl-style-build v0.9.0*
