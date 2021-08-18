pipeline {
agent{label 'worker1'}
stages{
stage("Build"){
steps{
sh '''
docker build -t nginx7 -f nginx7.dockerfile .
'''
}
}
stage("run"){
steps{
sh '''
docker rm -f nginx7 | exit 0
docker run -d -p 13456:80 --name nginx7 nginx7
'''
}
}
}
}
