# git代理设置
git config --global http.proxy http://127.0.0.1:1080

git config --global https.proxy https://127.0.0.1:1080

git config --global --unset http.proxy

git config --global --unset https.proxy

# pip代理设置
pip config set global.HTTPS_PROXY https://127.0.0.1:4438

pip config set global.HTTP_PROXY http://127.0.0.1:4438

# conda代理设置
conda config --set proxy_servers.http http://id:pw@address:port

conda config --set proxy_servers.https https://id:pw@address:port

# ubuntu代理设置
export http_proxy=http://proxy_ip:port     #代表http代理

export https_proxy=http://proxy_ip:port  #代表https代理

export ftp_proxy=http://proxy_ip:port  #代表ftp代理

# pip设置国内源
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple

# npm设置代理
npm config set proxy http://server:port

npm config set https-proxy http://server:port
