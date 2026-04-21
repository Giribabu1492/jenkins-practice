 sudo wget -O /etc/yum.repos.d/jenkins.repo \
 https://pkg.jenkins.io/redhat-stable/jenkins.repo


sudo yum install fontconfig java-21-openjdk


sudo yum install jenkins
sudo systemctl daemon-reload