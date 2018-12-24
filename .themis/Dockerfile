# 源镜像
FROM python:3.7.1-alpine

# Installing client libraries and any other package you need
RUN apk update && apk add libpq gcc libffi-dev musl-dev postgresql-dev make tzdata

# 设置时区
RUN /bin/cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo 'Asia/Shanghai' >/etc/timezone

# 使用阿里云的pip镜像,copy的文件属于当前dockerfile的相对目录
COPY pip.conf /root/.pip/pip.conf

COPY requirements.txt ./
RUN pip install -r requirements.txt