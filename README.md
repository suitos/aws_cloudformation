# aws_cloudformation



## aws cloudformation
인스턴스 자동 생성 + 기존 보안그룹 적용 + ip할당 + 신규 보안그룹 생성 후 적용
## AWS CLI
```
PROMPT> aws cloudformation create-stack \
  --stack-name {$stackName} \
  --template-body {$fileLocate}\awsStack.yaml \
  --parameters InstanceName=${instanceName},ImageId=${imageId},KeyName=${sshKeyName},InstanceType=${instanceType},
               SubnetId=${subnetId}, SecurityGroupIds=${securityGroupIds},SelectedVpcId=${selectedVpcId},NewIngressRules=${newIngressRules},
               NewEgressRules=${newEgressRules}
```

## 추가될 사항
paramValue null 일 경우 일부 단계 skip 필요
ex) 인바운드, 아웃바운드 지정 안할 경우 보안그룹 생성하는 단계 스킵
