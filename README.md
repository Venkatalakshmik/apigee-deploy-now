# apigee-deploy-now
Deploy Now button for Apigee Edge samples.

[![Deploy to Apigee](./images/deploy_to_apigee.png)](http://dabuttonfactory.com/#t=Deploy+to+Apigee&f=Calibri-Bold-Italic&ts=22&tc=fff&hp=35&vp=10&c=round&bgt=pyramid&bgc=f90&ebgc=f90&shs=4&shc=666&sho=se)

##### cURL to Github Repo
```shell
curl -X POST -H "Content-Type: application/x-www-form-urlencoded" -d 'repo=https%3A%2F%2Fgithub.com%2Fakoo1010%2Fapigee-tutorials.git' -d 'apiFolder=apiproxies%2Fapigee-nock-mock' -d 'makeScript=make.sh' \
-d 'org=testmyapi' -d 'env=test' -d 'userName='$ae_username'' -d 'pw='$ae_password'' 'http://localhost:3000/deploy' -v
```
##### cURL with zip file
```shell
curl -v -X POST -F "zipFile=@Mavendeploynow-master.zip" -F "makeScript=makeScript.sh" -F "apiFolder=Mavendeploynow-master/src/gateway/forecastweatherapi/" -F "org=testmyapi" -F "env=test" \
-F userName=$ae_username -F pw=$ae_password 'http://localhost:3000/deploy_zip'
```

##### Deployment through AWS EC2 instance
```shell
curl -v -X POST -F "zipFile=@/Users/ApigeeCorporation/Downloads/Mavendeploynow-master.zip" -F "makeScript=makeScript.sh" -F "apiFolder=Mavendeploynow-master/src/gateway/forecastweatherapi/" -F "org=testmyapi" -F "env=test" \
-F userName=$ae_username -F pw=$ae_password 'https://ec2-52-23-232-127.compute-1.amazonaws.com/deploy_zip' -k
```

##### Access Login App
http://localhost:3000/login-form/

##### Access Login App
https://ec2-52-23-232-127.compute-1.amazonaws.com/login-form/

##### Repo enabled with Deploy Now Button
Click on the "Deploy Now" button from [this page](https://github.com/dzuluaga/Mavendeploynow)

##### Access resources generated by make file
All builds will be created under ```builds/{org}-{env}``` folder.
http://localhost:3000/builds/testmyapi-test/README.md

##### Setup SSL for Node.js
Follow [these](http://blog.mgechev.com/2014/02/19/create-https-tls-ssl-application-with-express-nodejs/) steps

**Note: ae_username and ae_password can be replaced with an actual username and password.**