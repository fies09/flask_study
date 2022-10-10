1, 初始化数据库
python3 manage.py db init #初始化
python3 manage.py db migrate -m "init message" #提交变更
python3 manage.py db upgrade # 升级变更
2,日志管理模块,登录退出等
3,发布公告
4,创建管理员命令
python3 manage.py create_admin
5,启动redis
redis-server
6,部署
①打包环境
pip3 freeze > requirement.txt

②安装redis和mysql,更新和处理mysql和redis

③安装和配置nginx

apt install nginx

备份和修改default: /etc/nginx/sites-available/default

cp default default_bak

nginx -t

启动服务:

nohup  gunicorn -w 4 -b 0.0.0.0:5050 manage:app &

