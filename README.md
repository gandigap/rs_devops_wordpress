# rs_devops_wordpress

After complete `terraform apply` code from branch `task-5` project `https://github.com/gandigap/rsschool-devops-course-tasks/tree/task-5` you could run this GHA actions

And after success result you could set port forward connection complete commands
```sh
ssh k3s_server // on your locale machine
kubectl port-forward --namespace wordpress svc/wordpress 8081:80 & // after connect
```
and in aditional terminal complete command 
```sh
ssh -L 8081:localhost:8081 k3s_server
```
than you could open browser and open link `http://localhost:8081/wp-admin/install.php`
Screenshot I added in repository

Also you need secrets and vars for you repository for example:
```sh
secret K3S_IP=123.123.123.123
secret K3S_SSH_PK=public ssh key
secret K3S_USER=ec2-user
var SSH_CONFIG=from k3s.yaml
```