# ONLY FOR TEST
```
name: Test CD
on: [push]
jobs:

  build:
    name: Build
    runs-on: ubuntu-latest
    steps:
    - name: Push To Server
      uses: appleboy/ssh-action@master
      with:
        host: ${{ secrets.HOST }}
        username: ${{ secrets.USERNAME }}
        #password: ${{ secrets.PASSWORD }}
        port: ${{ secrets.PORT }}
        key: ${{ secrets.KEY }}
        script: |
         cd /var/www/html/
         touch test-action.txt
         echo "completed" > test-action.txt
```
test