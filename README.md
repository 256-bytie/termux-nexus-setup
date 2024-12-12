# **Revised-Guide-to-Run-Nexus-on-Termux**

**1. Preparation**
1 Ensure Termux is installed from a trusted source (like F-Droid or GitHub). 

**2. System Update**
Run a full update:
```bash
pkg update -y && pkg upgrade -y
```

**3. Install Required Tools**
```bash
pkg install -y git curl protobuf rust openssl
```

**4. Storage Access**
Allow Termux to access storage for project files:
```bash
termux-setup-storage
```
**5. Set Environment Variables
To simplify configuration, export all variables in a single script instead of typing them manually:
```bash
cat <<EOF > env_setup.sh
export OPENSSL_DIR=\$PREFIX
export OPENSSL_INCLUDE_DIR=\$PREFIX/include
export OPENSSL_LIB_DIR=\$PREFIX/lib
export PKG_CONFIG_ALLOW_SYSTEM_CFLAGS=1
export PKG_CONFIG_PATH=\$PREFIX/lib/pkgconfig
EOF

source env_setup.sh
```
Tip: The above script saves variables to env_setup.sh so you can run source env_setup.sh anytime you need them.

**6. 



