# 安装 GCP

下载 SDK

`https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-sdk-147.0.0-darwin-x86_64.tar.gz`

解压 SDK

`tar zxvf google-cloud-sdk-147.0.0-darwin-x86_64.tar.gz`

安装

`./google-cloud-sdk/install.sh`



```bash
# The next line updates PATH for the Google Cloud SDK.
if [ -f '/Users/xxx/google-cloud-sdk/path.zsh.inc' ]; then source '/Users/xxx/google-cloud-sdk/path.zsh.inc'; fi

# The next line enables shell command completion for gcloud.
if [ -f '/Users/xxx/google-cloud-sdk/completion.zsh.inc' ]; then source '/Users/xxx/google-cloud-sdk/completion.zsh.inc'; fi
```

SSH 登录

```bash
gcloud compute --project "gcloud-micro01" ssh --zone "asia-east1-a" "instance-1"
```


## 扩展阅读
* [ Cloud SDK Documentation  | Google Cloud Platform](https://cloud.google.com/sdk/docs/quickstart-mac-os-x)
