# git代理设置
git config --global http.proxy http://127.0.0.1:1080

git config --global https.proxy https://127.0.0.1:1080

# pip代理设置
pip config set global.HTTPS_PROXY https://127.0.0.1:4438

pip config set global.HTTP_PROXY http://127.0.0.1:4438

# ubuntu代理设置
export http_proxy=http://proxy_ip:port     #代表http代理

export https_proxy=http://proxy_ip:port  #代表https代理

export ftp_proxy=http://proxy_ip:port  #代表ftp代理

# pip设置国内源
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple

# npm设置代理
npm config set proxy http://server:port

npm config set https-proxy http://server:port
