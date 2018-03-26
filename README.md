# SFDX  App

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
