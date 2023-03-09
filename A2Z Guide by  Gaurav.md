# AWS introduction

## lac_3

# cloud computing service models

### on-permses :

- Iass (infastructure as a service): They provide hardware as well as operating system (e.g:Ec2 service)
- Pass (platform as a service ) : already everything setup ,do't need to configure them .
- saas (software as a services): there are too many services like: s3 bucket,dynamodb etc.

## lac_4

# Deploy model on clouds

- Private Clouds :won server
- Public Clouds :other company server use as a rent
- Hybrid Clouds : any company hold won server as well as they sell their server

## lac_5

## How aws charge

# \* key point

1. Compute : utilization
2. Storage : how much storage we use
3. data transfer : download and upload from out side (how much data sent server to clint or data store client to server)

n.b : with in n/w how much data transfer aws do't charge anything

## lac_6

# what and why is aws region

[![aws region -logo](https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.concurrencylabs.com%2Fblog%2Fchoose-your-aws-region-wisely%2F&psig=AOvVaw3iVkuq1X1nQxu_CWL3nwkD&ust=1678109976364000&source=images&cd=vfe&ved=0CBAQjRxqFwoTCLCy8P30xP0CFQAAAAAdAAAAABAJ)](.com)

- Region: till now 27 region on aws,with in one region minimum two availability zone and maximum six zone and aws try to avg three availability zone every region

- availability zone : on the availability zone data center present

## lac_7

# what and why is aws availability zone

## lac_8

# what and why is aws local zone

```
* local zone similar to availability zone but some advance feature provide local zone.i.e:less than 10ms latency.when you know your customer all are with in bangalore then you chouse your local zone bangalore that time bangalore customer access any server lessthan 10ms.

n.b : similar,here also have some draw fault you could access some feature not all feature.
```

## lac_10

# create ec2 instance

- Ec2 -> elsctice cloud computing
- Ec2 -> main core concept that ec2 provide server on rent,
  n.b: we also choase os,ram,rom ,n/w etc.

# create first Ec2 instance

- step1-> visit aws official page
- step2-> goto instance section
- step3-> goto to top-right conner and click "lunch new instance"
- step4-> open a instance template
- step5-> first input section name: chouse your instance name
- step5-> 2nd input section AMI(amazon machine image) -- application and os images : house any os as your requried(i.e:ubantu,windos,macos,etc) also you chouse architechure arm or intel(x86)--64-bit
- step5->3rd section instance type : t2 micoro,t2 small ...ect as your req\*
- step6->4th section key_pair:create or use exicting key, key that give you access your instance,key bacicaly private only \* youcould know your key.
- step7-> open key_pair template:1st->chouse your key pair name , 2nd-> chouse key pair type i) rsa always chouse,3rd-> file format always couse .pem file if your os less than window 10 then chousew .ppk file format.
- step8-> 5th network section: configure your n/w. by defaut allow ssh traffic from also checked and it akso accessany where 0.0.0.0
- step9->6th configure storage section: this is basicaly c drive thats it(root volume)

- step10-> final step click "lunch instance" -------> ready to use your instance

n.b:inbound and outbound ...discuss in letter

# lac-11

## access Ec2 instance from windows machine

step1-> goto Downlodaded file and open CMD
step2-> enter cmd

```
ssh -i key_name.prm
```

you could connect through browser -> goto connect to instance -> goto ssh client -> copy example

- show os details

```
cat /etc/os-release
```

- show architecture

```
lscpu
```

- show file system

```
df -h
```

- show ip configaration

```
ip -a
```

## Easy to connect Ec2 instance

step1-> goto instance ->click conncet-> Ec2 instsnce connect ->DONE

N.B :-> By default when instance we are create all instance set to ap-south1. but ,here question if every one create their instance on by default avilability zone then all instace create on ap_south1.then ap_south1 have heavy loaded . thats why when any instance create the availability zone mange internaly by AWS.

- any file read and write permission cmd

```
chmod 400 file name
```

# root user login

```
sudo -i
```

<!-- 4565 -->

# delete or terminate any instance

step 1-> goto instance
step2-> select instance
step3-> terminate instance

# lac_15

## aws security group

- security group provide you that all should allow your application.

# create your first security group

- step1-> goto security group section
- step2-> fill security group name
- step3-> give your applliaction description
- step4-> setup inbound rule
- 1. select application req\* type
- 2. chouse source who are allow
- n.b : we could chouse multiple rule
- N.B : one could have attach multiple security group.also , we could attach one security group many instance

# lac_16

# instance type

- instance type have 5 types
- more details ---> checkout instance type

# lac_20

instance metadata

# lac_21

## attach static ip

- if u set to application static ip then use elastic ip .
- elastic ip basicaly reserve your ip.
- step1-> create your elastic ip
- step2-> attach elactic ip to your instance
- goto elactic ip section and -> goto action section -> goto associate Eastic ip add
  n.b:: at most 5 elactic ip address we could set,if beyond any requried to add more than 5 elactic ip then one more step requried we discuss letter.
#lac 22