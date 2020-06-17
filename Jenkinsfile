import hudson.model.*;
def getdate(){//返回当天日期
return new Date().format('yyyy-MM-dd hh:mm:ss')
}

pipeline{

    agent  any

    stages{

        stage('1-'){

            
            steps{

                echo 'Hello World !'
                //dir('D:\\Devops\\交易节点一'){
                //    stash includes: '', name: '节点一退补款文件'
                //}
            }
        }

        stage('2-'){

            parallel{

                stage('Branch A'){

                    

                    environment{
                        filename='1111'
                        filesno='20'
                        dbfrec='行数'
                        success_result='10'
                        fail_result='20'
                        file1='111'
                    }

                    stages{

                        stage('A1'){

                            steps{

                                script{

                                    file1='222'
                                    echo "file1::${file1}"
                                    echo 'A1'
                                    //dir('C:\\银河\\节点一'){
                                    //    unstash '节点一退补款文件'
                                    //}
                                }
                            }
                        }

                        stage('A2'){

                            steps{
                                echo 'A2'
                                echo "file1::${file1}"
                                error 'A'
                            }
                        }
                    }

                    post{

                        success{

                            script{
                                date=getdate()
                                bat label:'输出处理结果',script:"@echo ${date} 完成集中交易节点一ETF退补款文件处理，结果如下：【${filename}】导入成功！文件编号：【${filesno}】，文件行数：【${dbfrec}】，处理成功数量：【${success_result}】，处理失败数量：【${fail_result}】"
                                echo "ETF退补款构建成功！"
                            }
                        }
                        failure{
                            echo 'fail'
                        }
                    }
                }

                stage('Branch B'){

                    
                    steps{
                        echo "On Branch B"
                    }
                    post{

                        success{
                            echo 'success'
                        }
                        failure{
                            echo 'fail'
                        }
                    }
                }
            }
        }
    }
}
