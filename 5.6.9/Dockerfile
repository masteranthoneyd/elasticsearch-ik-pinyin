FROM docker.elastic.co/elasticsearch/elasticsearch:5.6.9
MAINTAINER yangbingdong <yangbingdong1994@gmail.com>
ARG TZ 
ARG HTTP_PROXY
ENV TZ=${TZ:-"Asia/Shanghai"} http_proxy=${HTTP_PROXY} https_proxy=${HTTP_PROXY}
COPY char_filter_text.txt /usr/share/elasticsearch/config/
RUN bin/elasticsearch-plugin install https://github.com/medcl/elasticsearch-analysis-ik/releases/download/v5.6.9/elasticsearch-analysis-ik-5.6.9.zip \
  && bin/elasticsearch-plugin install https://github.com/medcl/elasticsearch-analysis-pinyin/releases/download/v5.6.9/elasticsearch-analysis-pinyin-5.6.9.zip \
  && bin/elasticsearch-plugin install https://github.com/medcl/elasticsearch-analysis-stconvert/releases/download/v5.6.9/elasticsearch-analysis-stconvert-5.6.9.zip
#  && ln -snf /usr/share/zoneinfo/$TZ /etc/localtime \
#  && echo $TZ > /etc/timezone
ENV http_proxy=
ENV https_proxy=

