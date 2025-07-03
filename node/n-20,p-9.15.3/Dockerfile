FROM node:20-alpine

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories # buildkit
RUN apk --no-cache add tzdata &&     cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime &&     echo "Asia/Shanghai" > /etc/timezone # buildkit
ENV TZ=Asia/Shanghai
RUN apk --no-cache add ca-certificates   && update-ca-certificates # buildkit
RUN apk add curl # buildkit
RUN curl --version # buildkit
RUN apk add unzip # buildkit
ENV TZ=Asia/Shanghai
RUN apk add git # buildkit

# 设置工作目录
WORKDIR /home/noroot/app
RUN corepack enable && corepack prepare pnpm@9.15.3 --activate && npm config set registry https://registry.npmmirror.com && pnpm config set registry https://registry.npmmirror.com