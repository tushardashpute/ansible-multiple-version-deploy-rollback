# ansible-multiple-version-deploy-rollback
# I used below repo for the example

git clone https://github.com/tushardashpute/springboohello-CICD.git
cd springboohello-CICD/
mvn clean install

# For the initial setup use the below it will create service file using jinja template
update_spring_boot.yaml -e "version=0.1.0"

# To start deployment with different versions
ansible-playbook start_deploy.yml -e "version=0.2.0"

# To rollback to the previos version
ansible-playbook start_deploy.yml -e rollback=true
