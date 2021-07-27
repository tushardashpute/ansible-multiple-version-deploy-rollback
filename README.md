# ansible-multiple-version-deploy-rollback
# I used below repo for the example

git clone https://github.com/tushardashpute/springboohello-CICD.git
cd springboohello-CICD/
mvn clean install

# To start deployment with different versions
ansible-playbook start_deploy.yml -e "version=0.1.0"

# To rollback to the previos version
ansible-playbook start_deploy.yml -e rollback=true
