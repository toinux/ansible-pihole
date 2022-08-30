sudo apt-add-repository ppa:ansible/ansible

ansible-galaxy install -r requirements.yaml

sudo mkdir /etc/gravity-sync
sudo chmod 775 /etc/gravity-sync
sudo git clone https://github.com/vmstan/gravity-sync.git /etc/gravity-sync/.gs
sudo cp /etc/gravity-sync/.gs/gravity-sync /usr/local/bin

# une seule fois sur le master
gravity-sync push
gravity-sync auto