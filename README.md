FROM tiangolo/nginx-rtmp

COPY nginx.conf /etc/nginx/nginx.conf
rtmp {
    server {
        listen 1935;
        chunk_size 4096;

        application live {
            live on;
            record off;
        }
    }
}
