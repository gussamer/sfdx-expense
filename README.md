# SFDX  App

https://salesforce.mimeo.digital/

## Dev, Build and Test


## Resources


## Description of Files and Directories


## Issues

    1  cd sfdx-maria/
    2  ls
    3  chmod -R u+w force-app
    4  git status
    5  git log
    6  sfdx force:org:create -a sfdx-maria -s -f config/project-scratch-def.json 
    7  sfdx force:source:status
    8  sfdx force:source:push
    9  sfdx force:user:permset:assign -n Dreamhouse
   10  sfdx force:data:tree:import -u sfdx-maria -f assets/data/Broker__c-Property__c.json
   11  history
   12  sfdx force:org:open
   13  sfdx force:source:status
   14  sfdx force:source:pull
   15  sfdx force:apex:test:run -c -r human -w 10
   16  git add .
   17  git commit -m "added gallery"
   18  git push -u origin feature-maria-gallery
   19  git log
   20  git checkout master
   21  git pull
   22  git log
   23  sfdx force:source:convert -d assets/mdapi
   24  sfdx force:mdapi:deploy -d assets/mdapi -u sanddev -w 10
   25  sfdx force:apex:test:run -c -r human -w 10
   26  sfdx force:mdapi:deploy -d assets/mdapi -u sanddev -w 10 --testlevel
   27  sfdx force:mdapi:deploy -d assets/mdapi -u sanddev -w 10 --testlevel local
   28  sfdx force:mdapi:deploy --help
   29  sfdx force:mdapi:deploy -d assets/mdapi -u sanddev -w 10 --testlevel RunLocalTests
   30  sfdx force:data:tree:import -u sfdx-sandbox -f assets/data/Broker__c-Property__c.json
   31  sfdx force:data:tree:import -u sanddev -f assets/data/Broker__c-Property__c.json
   32  sfdx force:org:open -u sfdx-sandbox
   33  sfdx force:org:open -u sanddev
   34  sfdx force:mdapi:deploy -d assets/mdapi -u sfdx-prod -w 10 --testlevel RunLocalTests
   35  sfdx force:mdapi:deploy -d assets/mdapi -u devhub -w 10 --testlevel RunLocalTests
   36  sfdx force:org:open -u devhub
   37  cd ..
   38  sfdx force --help
   39  sfdx force:project
   40  sfdx force:project --help
   41  sfdx force:project:create sfdx-expense
   42  sfdx force:project:create -n sfdx-expense
   43  cd sfdx-expense/
   44  ls
   45  curl -u gussamer https://api.github.com/user/repos -d '{"name":"'sfdx-expense'"}'
   46  git init
   47  vim .gitignore
   48  git remote add origin https://github.com/gussamer/sfdx-expense.git
   49  chmod -R u+w Expense
   50  sfdx force:package2:create -n Expense -o Unlocked
   51  git add .
   52  git commit -m "Initial commit of Expense app metadata"
   53  git push -u origin master
   54  sfdx force:package2:version:create -i 0Ho6A000000XZAbSAO -d Expense -w 10
   55  sfdx force:package2:version:list
   56  git tag v1.0.0.1 && git push --tags
   57  sfdx force:package2:version:list
   58  sfdx force:package:install -i 04t6A000002Q2a1QAC -u sanddev -p 10 -w 10
   59  sfdx force:user:permset:assign -u sanddev -n Expense_Tracker
   60  sfdx force:data:tree:import -u sanddev -f assets/data/Expense__c.json
   61  sfdx force:org:open -u sanddev
   62  sfdx force:mdapi --help
   63  sfdx force:mdapi:deploy --help
   64  history
   65  history >> README.md
   66  git add .
   67  git commit -m "added view button to expense cards"
   68  git push -u origin master
   69  sfdx force:package2:list
   70  sfdx force:package2:version:create -i 0Ho6A000000XZAbSAO -d Expense -w 10
   71  sfdx force:package2:version:list
   72  sfdx force:org:open -u sanddev
   73  sfdx force:package2:version:list
   74  sfdx force:package2:version:list
   75  sfdx force:package:install -i 04t6A000002Q3eAQAS -u devhub -p 10 -w 10
   76  sfdx force:package2:version:update -i 05i6A000000TN1yQAG --setasreleased --noprompt
   77  sfdx force:package:install -i 04t6A000002Q3eAQAS -u devhub -p 10 -w 10
   78  cd certs/
   79  openssl genrsa -des3 -passout pass:x -out server.pass.key 2048
   80  openssl rsa -passin pass:x -in server.pass.key -out server.key
   81  rm server.pass.key
   82  kls
   83  ls
   84  openssl req -new -key server.key -out server.csr
   85  ls
   86  openssl x509 -req -sha256 -days 365 -in server.csr -signkey server.key -out server.crt
   87  echo "$(pwd)/server.key"
   88  sfdx force:org:open -u devhub
   8
   90  export CONSUMER_KEY=
   91  export JWT_KEY_FILE="~/Documents/sfdx/sfdx-expense/certs/server.key"
   92  export DEVHUB_USERNAME=angusa@trailheadx.com
   93  sfdx force:auth:jwt:grant -i ${CONSUMER_KEY} -f ${JWT_KEY_FILE} -u ${DEVHUB_USERNAME} -a sfdx-prod -d
   94  export JWT_KEY_FILE="./server.key"
   95  sfdx force:auth:jwt:grant -i ${CONSUMER_KEY} -f ${JWT_KEY_FILE} -u ${DEVHUB_USERNAME} -a sfdx-prod -d
   96  export CONSUMER_KEY=3055324253338705468
   97  sfdx force:auth:jwt:grant -i ${CONSUMER_KEY} -f ${JWT_KEY_FILE} -u ${DEVHUB_USERNAME} -a sfdx-prod -d
   98  export CONSUMER_KEY=
   99  sfdx force:auth:jwt:grant -i ${CONSUMER_KEY} -f ${JWT_KEY_FILE} -u ${DEVHUB_USERNAME} -a sfdx-prod -d
  100  sfdx force:auth:jwt:grant -i ${CONSUMER_KEY} -f ${JWT_KEY_FILE} -u ${DEVHUB_USERNAME} -a sfdx-prod -d
  101  sfdx force:auth:jwt:grant -i ${CONSUMER_KEY} -f ${JWT_KEY_FILE} -u ${DEVHUB_USERNAME} -a devhub -d
  102  sfdx force:auth:jwt:grant -i ${CONSUMER_KEY} -f ${JWT_KEY_FILE} -u ${DEVHUB_USERNAME} -a sfdx-prod -d --instanceurl https://battlestar-x-wing-128204.my.salesforce.com
  103  sfdx force:auth:jwt:grant -i ${CONSUMER_KEY} -f ${JWT_KEY_FILE} -u ${DEVHUB_USERNAME} -a sfdx-prod -d --instanceurl https://battlestar-x-wing-128204.my.salesforce.com
  104  sfdx force:auth:jwt:grant -i ${CONSUMER_KEY} -f ${JWT_KEY_FILE} -u ${DEVHUB_USERNAME} -a sfdx-prod -d --instanceurl https://battlestar-x-wing-128204.my.salesforce.com
  105  sfdx force:auth:jwt:grant -i ${CONSUMER_KEY} -f ${JWT_KEY_FILE} -u ${DEVHUB_USERNAME} -a devhub -d --instanceurl https://battlestar-x-wing-128204.my.salesforce.com
  106  sfdx force:auth:jwt:grant -i ${CONSUMER_KEY} -f ${JWT_KEY_FILE} -u ${DEVHUB_USERNAME} -a devhub -d --instanceurl https://battlestar-x-wing-128204.my.salesforce.com
  107  echo "$(pwd)/server.key"
  108  export JWT_KEY_FILE=/c/Users/Admin/Documents/sfdx/sfdx-expense/certs/server.key
  109  sfdx force:auth:jwt:grant -i ${CONSUMER_KEY} -f ${JWT_KEY_FILE} -u ${DEVHUB_USERNAME} -a devhub -d --instanceurl https://battlestar-x-wing-128204.my.salesforce.com
  110  export CONSUMER_KEY=
  111  sfdx force:auth:jwt:grant -i ${CONSUMER_KEY} -f ${JWT_KEY_FILE} -u ${DEVHUB_USERNAME} -a devhub -d --instanceurl https://battlestar-x-wing-128204.my.salesforce.com
  112  export CONSUMER_KEY=
  113  sfdx force:auth:jwt:grant -i ${CONSUMER_KEY} -f ${JWT_KEY_FILE} -u ${DEVHUB_USERNAME} -a devhub -d --instanceurl https://battlestar-x-wing-128204.my.salesforce.com
  114  openssl genrsa -des3 -passout pass:x -out server.pass.key 2048
  115  openssl rsa -passin pass:x -in server.pass.key -out server.key
  116  openssl req -new -key server.key -out server.csr
  117  openssl x509 -req -sha256 -days 365 -in server.csr -signkey server.key -out server.crt
  118  echo "$(pwd)/server.key"
  119  export CONSUMER_KEY=
  120  export JWT_KEY_FILE="/c/Users/Admin/Documents/sfdx/sfdx-expense/certs/server.key"
  121  export DEVHUB_USERNAME=angusa@trailheadx.com
  122  sfdx force:auth:jwt:grant -i ${CONSUMER_KEY} -f ${JWT_KEY_FILE} -u ${DEVHUB_USERNAME} -a devhub -d --instanceurl https://battlestar-x-wing-128204.my.salesforce.com
  123  sfdx force:auth:jwt:grant -i ${CONSUMER_KEY} -f ${JWT_KEY_FILE} -u ${DEVHUB_USERNAME} -a devhub -d --instanceurl https://battlestar-x-wing-128204.my.salesforce.com
  124  cd ../..
  125  ls
  126  cd sfdx-maria/
  127  ls
  128  git checkout master
  129  git pull
  130  travis login --org
  131  travis repos --active --no-interactive -m '*/trailheadx18'
  132  git config --local travis.slug gussamer/trailheadx18
  133  export SERVER_KEY_PASS=gr3yf0x5
  134  travis encrypt SERVER_KEY_PASS=$SERVER_KEY_PASS --add
  135  openssl aes-256-cbc -k $SERVER_KEY_PASS -in
  136  openssl aes-256-cbc -k $SERVER_KEY_PASS -in assets/server.key -out assets/server.key.enc
  137  rm assets/server.key
  138  travis env set CONSUMER_KEY $CONSUMER_KEY
  139  travis env set CONSUMER_KEY 
  140  travis env set DEVHUB_USERNAME $DEVHUB_USERNAME
  141  git add .
  142  git commit -m "Added Travis CI"
  143  git push -u origin master
  144  travis open
  145  cd ..
  146  ls
  147  cd sfdx-expense/
  148  ls
  149  history >> README.md
