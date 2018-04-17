# aws cli를 이용한 angular deploy

1. #### [python3 설치](https://www.python.org/downloads/release/python-361/)

2. #### pip3 설치

   ```
   $ curl -O https://bootstrap.pypa.io/get-pip.py
   $ python3 get-pip.py --user
   ```


3. AWS CLI 설치

   ```
   $ pip3 install awscli --upgrade --user
   ```

4. AWS CLI 설치 확인

   ```
   $ aws --version
   AWS CLI 1.11.84 (Python 3.6.1)
   ```

   bash: aws: command not found 일때 경로를 재설정

   ```
   $ which python
   /usr/local/bin/python
   ```

   혹은

   ```
   $ pip3 install awscli --upgrade --user
   Requirement already up-to-date: awscli in ./Library/Python/3.6/lib/python/site-packages
   ...
   ```

   재 실행을 통해 aws cli의 설치경로를 확인한다.

   위의 경우 실제로 경로는 ***./Library/Python/3.6/bin*** 에 있다.

5. .bash_profile 확인 후 수정

   ```
   $ ls -a ~
   .  ..  .bash_logout  .bash_profile  .bashrc  Desktop  Documents  Downloads
   $ vi ~./bash_profile
   ```

   ```
   ...
   export PATH=/Users/ikoobmacmini_01/Library/Python/3.6/bin:$PATH
   ...
   ```

   .bash_profile을 세션에 로드

   ```\
   $ source ~/.bash_profile
   ```

6. access key, security key 입력

   ```
   $ aws configure
   ```

7. S3 bucket list 확인

   ```
   $ aws s3 ls
   ```
   ### Error

   ```Shell
   $ aws s3 ls
   An error occurred (AccessDenied) when calling the ListBuckets operation: Access Denied
   ```

   권한의 문제이다. 해결방법은 다음과 같다.

   1. AWS IAM
   2. 사용자
   3. 권한
   4. 권한추가
   5. 기존 정책 직접 연결
   6. AmazonS3FullAccess 클릭

   aws cli는 사용자의 정보를 가지고 있는데, 그 사용자에게 권한이 부여되지 않으면 위와 같은 오류가 발생한다. 사용자에게 직접 권한을 부여해주어야 한다.

   ​

8. 배포파일 s3에 deploy 

   ```
   $ aws s3 cp ./dist s3://BUCKETNAME --recursive --acl public-read
   ```

   ​