 docker build -t  pytorch_ruoli:20230721 --force-rm -f Dockerfile .
 docker tag pytorch_ruoli:20230721 docker-reg.devops.xiaohongshu.com/media/pytorch_ruoli:20230721
 docker push docker-reg.devops.xiaohongshu.com/media/pytorch_ruoli:20230721