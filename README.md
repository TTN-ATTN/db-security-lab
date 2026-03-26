## Setup
### Prerequisite
- Docker
- Docker compose
- Python3, pip
### Phase 1
#### Packages
```
sudo apt update && sudo apt upgrade -y
sudo apt install -y \
  ca-certificates curl wget git jq tree unzip \
  python3 python3-pip python3-venv
```
#### Containers
```
docker compose build
docker compose up -d
```

#### Python venv
```
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```
#### Mysql workbench
```
cd /tmp
wget https://dev.mysql.com/get/mysql-apt-config_0.8.36-1_all.deb
sudo dpkg -i mysql-apt-config_0.8.36-1_all.deb
sudo apt update
sudo apt install -y mysql-workbench-community
```

#### Check
```
cd ~/db-security-lab
set -a
source .env
set +a

docker compose ps

docker exec dbsec-mysql \
  mysql -uroot -p"${MYSQL_ROOT_PASSWORD}" \
  -e "SELECT VERSION() AS mysql_version, CURRENT_USER() AS current_user;"

curl -fsS http://127.0.0.1:9104/metrics | sed -n '1,10p'
curl -fsS http://127.0.0.1:9090/-/ready && echo
curl -fsS http://127.0.0.1:3000/api/health && echo
```