         **********PROCEDURE TO HOST A STATIC WEBPAGE IN AWS************


Create a s3 bucket that bucket have public access policy
![Screenshot from 2024-03-24 09-08-25](https://github.com/kalaiprasanth/AWS--static-website/assets/161060613/94a452ce-8c26-4bdd-bc70-cd1f7b621647)

Upload a object like index.html in s3 bucket


Create a role in IAM for for accessing EC2 to S3 .

![Screenshot from 2024-03-24 10-04-49](https://github.com/kalaiprasanth/AWS--static-website/assets/161060613/a8f668f2-02d6-41e3-afe4-2dc9b918221c)

Create a EC2 instance & Connect the instance into local terminal #ssh -i keypair.pem username@public ip
![Screenshot from 2024-03-24 10-41-41](https://github.com/kalaiprasanth/AWS--static-website/assets/161060613/f8847419-cbdf-44d3-ada9-c9320642e7b6)

After creating a instance attach role for access s3 bucket into ec2

![Screenshot from 2024-03-24 10-38-36](https://github.com/kalaiprasanth/AWS--static-website/assets/161060613/ce89f0c0-ba51-4ece-a1f8-e650b1a2645f)

Then Go to our instance start a webserver like nginx,httpd...
Commands#
       * sudo apt update
       * sudo apt-get install nginx
       * sudo service nginx start
       * sudo service nginx status

    Now you see a webserver Running Status.....
![Screenshot from 2024-03-24 10-45-18](https://github.com/kalaiprasanth/AWS--static-website/assets/161060613/b6b12fc1-bd5a-4c31-b979-a8d491131e6c)


Then see your s3 bucket on instance terminal CMD# aws s3 ls
Copy s3 object into our #cd /var/www/html Using this CMD# aws s3 cp --recursive s3://sktechpro .


![Screenshot from 2024-03-24 12-54-46](https://github.com/kalaiprasanth/AWS--static-website/assets/161060613/20abfe24-46f0-4d38-8460-56cfc9e82529)

Copy Your Public IP and paste on Browser

The Final Output for AWS Static-website


![Screenshot from 2024-03-24 12-57-28](https://github.com/kalaiprasanth/AWS--static-website/assets/161060613/975c53d2-5c8c-4be2-909e-ab024299bd00)
