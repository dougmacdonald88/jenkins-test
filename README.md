# jenkins-test
docker container run -d \
    -p 8080:8080 \
    -v jenkins_files:/var/jenkins_home \
    --name jenkins-local \
    jenkins/jenkins



docker container exec \
    jenkins-local \
    sh -c "cat /var/jenkins_home/secrets/initialAdminPassword"


git commit -m ‘AddingFiles’
git remote add origin hhttps://github.com/dougmacdonald88/jenkins-test.git
git push -u origin main
git push origin main

