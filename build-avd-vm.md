# Basic steps to build an AVD host on an ACT generic node

``` bash
git config --global user.name "Mark Thiel"
git config --global user.email "mthiel117@gmail.com"

sudo apt-get update
sudo apt install python3-pip -y
python3 -m pip install --upgrade pip

pip3 install "ansible-core>=2.15.5,<2.16"

ansible-galaxy collection install arista.avd
export ARISTA_AVD_DIR=$(ansible-galaxy collection list arista.avd --format yaml | head -1 | cut -d: -f1)
pip3 install -r ${ARISTA_AVD_DIR}/arista/avd/requirements.txt

# Zsh
sudo apt-get install -y zsh
sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"
```
