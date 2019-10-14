# minidoc

    docker run -p 8181:8181 \
    --restart always   \
    --privileged=true   \
    --name web_app_mindoc \
    -e MINDOC_RUN_MODE=prod  \
    -e MINDOC_DB_ADAPTER=sqlite3  \
    -e MINDOC_DB_DATABASE=./database/mindoc.db  \
    -e MINDOC_CACHE=true  \
    -e MINDOC_CACHE_PROVIDER=file  \
    -e MINDOC_ENABLE_EXPORT=ture  \
    -e httpport=8181 \
    -v /root/web_app_mindoc/mindoc/database:/mindoc/database \
    -v /root/web_app_mindoc/mindoc/uploads:/mindoc/uploads \
    -d registry.cn-hangzhou.aliyuncs.com/mindoc/mindoc:v2.0-beta.2
