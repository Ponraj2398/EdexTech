<template>
  <q-page>
    <section>
      <div>
        <q-carousel v-model="slide" transition-prev="scale" infinite :autoplay="autoplay" @mouseenter="autoplay = false"
          @mouseleave="autoplay = true" transition-next="scale" animated control-color="orange" navigation padding arrows
          style="height: 95vmin;" class="bg-dark text-white">
          <template v-slot:navigation-icon="{ active, btnProps, onClick }">
            <q-btn v-if="active" size="lg" icon="home" color="yellow" flat round dense @click="onClick" />
            <q-btn v-else size="sm" :icon="btnProps.icon" color="white" flat round dense @click="onClick" />
          </template>

          <q-carousel-slide :name="1" class="column no-wrap flex-center img-fluid" img-src="../assets/awsimg.png"
            style="background-position: center;background-attachment: fixed;object-fit: contain;height: 50vmin;overflow: hidden;overflow-y: hidden;overflow-x: hidden;">
            <div class="q-pa-md example-row-equal-width">
              <div class="row">
                <div class="col-12 q-pa-md q-gutter-sm text-center">
                  <h2 style="font-size: 6vw;line-height: 7vw;color:#CDA45E;font-family: 'Times New Roman', Times, serif;">
                    <strong>AWS Training and Certification</strong>
                  </h2>
                  <h4
                    style="font-family: Amazon Ember Display, Helvetica Neue, Helvetica, Arial, sans-serif;font-size: 3vw;line-height: 7vw;">
                    <img class="q-pa-xs" src="https://miro.medium.com/v2/resize:fit:559/0*G5LoDNkO9UbO0F7j.png"
                      style="width: 25vmin;" />
                  </h4>
                  <q-btn style="font-size: 2vmin;" glossy color="deep-orange" class="text-capitalize"
                    label="Explore Digital training" rounded />
                  <q-btn style="font-size: 2vmin;" glossy label="Develop your team" class="text-capitalize" outline
                    rounded color="white" />
                </div>
                <!-- <div class="col-4 col-md-4">
                  </div> -->
              </div>
            </div>
          </q-carousel-slide>
          <q-carousel-slide :name="2" class="column no-wrap flex-center img-fluid" img-src="../assets/awsimg2.png"
            style="background-position: center; background-attachment: fixed;object-fit: contain;height: 50vmin;overflow: hidden;overflow-y: hidden;overflow-x: hidden;">
            <div class="q-pa-md example-row-equal-width">
              <div class="row">
                <div class="col-12 col-md-10 q-pa-md q-gutter-sm text-center">
                  <h2 style="font-size: 6vw;line-height: 7vw;color:#CDA45E;font-family: 'Times New Roman', Times, serif;">
                    <strong>AWS Academy</strong>
                  </h2>
                  <h4 style="font-family: 'Times New Roman', Times, serif;font-size: 3vw;line-height: 4vw;">
                    Empowering
                    higher education institutions to prepare students for industry-recognized
                    certifications and careers
                    in
                    the cloud</h4>
                  <q-btn style="font-size: 2vmin;" glossy color="deep-orange" class="text-capitalize"
                    label="Fill out institution application" rounded />
                </div>
                <!-- <div class="col-2 col-md-4">
                  </div> -->
              </div>
            </div>
          </q-carousel-slide>
          <q-carousel-slide :name="3" class="column no-wrap flex-center img-fluid slide3" img-src="../assets/awsimg3.png"
            style="background-position: center;background-attachment: fixed;object-fit: contain;height: 50vmin;overflow: hidden;overflow-y: hidden;overflow-x: hidden;">
            <div class="q-pa-md example-row-equal-width">
              <div class="row">
                <div class="col-12 q-pa-md q-gutter-sm text-center">
                  <h2 style="font-size: 6vw;line-height: 7vw;color:#CDA45E;font-family: 'Times New Roman', Times, serif;">
                    <strong>AWS Cloud Institute</strong>
                  </h2>
                  <h4 style="font-family: 'Times New Roman', Times, serif;font-size: 3vw;line-height: 4vw;">
                    The virtual
                    cloud-skills training program that will help you launch your career as a cloud
                    developer in as
                    little as
                    one year - regardless of your technical background. Come build the in-demand skills
                    that put YOU in
                    demand.</h4>
                  <!-- <q-btn glossy style="font-size: 2vmin;" color="deep-orange" class="text-capitalize"
                                        label="Apply Now" rounded /> -->
                </div>
                <!-- <div class="col-2 col-md-4">
                  </div> -->
              </div>
            </div>
          </q-carousel-slide>
        </q-carousel>
      </div>
    </section>
    <section style="background: #f6f6fa;font-family: 'Times New Roman', Times, serif;">
      <div class="container-fluid">
        <div class="row q-pa-sm">
          <div class="col-12 col-sm-6 col-md-4" v-for="e in enrollnow" :key="e">
            <div class="imagebox">
              <div class="box-wrapper">
                <div class="box-image">
                  <img :src="e.img" alt="" width="350px" height="250px" loading="lazy" />
                </div>
                <div class="box-header">
                  <h5 class="box-title" style="font-size:1rem;">{{ e.title }}</h5>
                </div>
                <div class="box-content">
                  <div class="box-desc" style="font-size:1rem;">
                    {{ e.paragraph }}
                    <div class="q-pa-md q-gutter-sm">
                      <q-btn label="Enroll Now" class="bg-deep-orange text-white" @click="bar2 = true" />
                      <q-dialog v-model="bar2" persistent transition-show="flip-down" transition-hide="flip-up">
                        <q-card class="bg-primary text-white">
                          <q-bar>
                            <q-space />

                            <q-btn dense flat icon="close" v-close-popup>
                              <q-tooltip class="bg-white text-primary">Close</q-tooltip>
                            </q-btn>
                          </q-bar>
                          <!-- <div class="login"> -->
                          <q-card-section>
                            <div class="text-h6">
                              <h4 class="login-para"
                                style="font-size: 1.4rem;font-family: 'Times New Roman', Times, serif;">Be the First one
                                to join
                                in EdexTech</h4>
                            </div>
                          </q-card-section>

                          <q-card-section class="q-pt-none">
                            <form action="#" method="">
                              <div class="form-content">
                                <div class="forms">
                                  <img src="../assets/login.png" alt="#" width="35"
                                    height="36" style="color: transparent;">
                                  <input type="text" id="fullname" name="fullname" placeholder="Fullname" required />
                                </div>
                                <div class="forms">
                                  <img src="../assets/gmail.png" alt="#" width="33"
                                    height="33" style="color: transparent;">
                                  <input type="email" id="email" name="email" placeholder="Email" required />
                                </div>
                                <div class="forms">
                                  <img src="../assets/whatapp.png" alt="#"
                                    width="33" height="33" style="color: transparent;">
                                  <input type="tel" id="phone" name="phone" placeholder="Mobile Number" required />
                                </div>
                                <div class="forms">
                                  <img src="../assets/location.png" alt="#"
                                    width="33" height="33" style="color: transparent;">
                                  <select name="state" id="state" required>
                                    <option disabled value="State" selected style="cursor:not-allowed">State</option>
                                    <option>Andaman and Nicobar Islands</option>
                                    <option>Andhra Pradesh</option>
                                    <option>Arunachal Pradesh</option>
                                    <option>Assam</option>
                                    <option>Bihar</option>
                                    <option>Chandigarh</option>
                                    <option>Chhattisgarh</option>
                                    <option>Dadra and Nagar Haveli and Daman and Diu</option>
                                    <option>Delhi</option>
                                    <option>Goa</option>
                                    <option>Gujarat</option>
                                    <option>Haryana</option>
                                    <option>Himachal Pradesh</option>
                                    <option>Jammu and Kashmir</option>
                                    <option>Jharkhand</option>
                                    <option>Karnataka</option>
                                    <option>Kerala</option>
                                    <option>Ladakh</option>
                                    <option>Lakshadweep</option>
                                    <option>Madhya Pradesh</option>
                                    <option>Maharashtra</option>
                                    <option>Manipur</option>
                                    <option>Meghalaya</option>
                                    <option>Mizoram</option>
                                    <option>Nagaland</option>
                                    <option>Odisha</option>
                                    <option>Puducherry</option>
                                    <option>Punjab</option>
                                    <option>Rajasthan</option>
                                    <option>Sikkim</option>
                                    <option>Tamil Nadu</option>
                                    <option>Telangana</option>
                                    <option>Tripura</option>
                                    <option>Uttar Pradesh</option>
                                    <option>Uttarakhand</option>
                                    <option>West Bengal</option>
                                  </select>
                                </div>
                              </div>
                              <div class="text-center"><q-btn glossy label="Submit" color="purple" /></div>
                            </form>
                          </q-card-section>
                          <!-- </div> -->
                        </q-card>
                      </q-dialog>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section>
      <div class="text-center" style="font-family:Verdana, Geneva, Tahoma, sans-serif;">
        <h3 style="font-size: 5vmin;font-family: 'Times New Roman', Times, serif;">Features of AWS Course</h3>
      </div>
      <div class="q-pa-md example-row-mix-and-match">
        <!-- Columns start at 50% wide on mobile and bump up to 33.3% wide on desktop -->
        <div class="row">
          <div class="col-12 col-sm-6 col-md-4 cards" v-for="c in cards" :key="c">
            <div class="card shadow-amber-2" :style="{ background: c.color }">
              <div class="q-pa-md">
                <span class="material-symbols-outlined" style="font-size:2rem;">
                  {{ c.icon }}
                </span>
                <!-- <q-icon :name="c.icon"> </q-icon> -->
                <h5 style="font-size:1.5rem;"><strong>{{ c.title }}</strong></h5>
                <p style="font-size:1.2rem;font-family: 'Times New Roman', Times, serif;">{{ c.desc }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section>
      <div class="skills q-pa-xs q-ma-xl q-gutter-xs">
        <div class="skills-covered" style="margin-bottom: 20px;">
          <h3 class="q-headline text-center" style="font-family: 'Times New Roman', Times, serif;">Skills Covered
          </h3>
          <div class="row skill q-gutter-sm flex justify-center">
            <div class="col-12 col-sm-4 col-md-3 skill-items" v-for="s in skills">
              <div>
                <p class="m-0">{{ s.sk }}</p>
              </div>
            </div><br>
          </div>
        </div>
      </div>
    </section>
    <section>
      <div class="q-ma-xl q-pa-xs q-ma-xl q-gutter-xs skills">
        <div class="q-gutter-sm skills-covered" style="width: 100%;height: auto;">
          <div class="text-center" style="font-family: 'Times New Roman', Times, serif;font-size: 1rem;">
            <h3>AWS Course Syllabus</h3>
          </div>
          <q-card>
            <q-tabs v-model="tab" dense class="bg-grey-9 text-white" active-color="orange-5" indicator-color="purple"
              align="justify">
              <q-tab name="module1-module5"><span class="text-center flex justify-center items-center">Module1
                  -
                  Module5</span></q-tab>
              <q-tab name="module6-module10"><span class="text-center flex justify-center items-center">Module6 -
                  Module10</span></q-tab>
              <q-tab name="self-paced"><span
                  class="text-center flex justify-center items-center">Self-Paced-Learnings</span></q-tab>
            </q-tabs>

            <q-tab-panels v-model="tab" animated class="bg-yellow-2 text-dark">
              <q-tab-panel name="module1-module5" style="font-family:Arial, Helvetica, sans-serif;">
                <div class="text-h6"><strong>Module 01 - Introduction to Cloud Computing and AWS</strong>
                </div> <br>
                <strong>1.1 </strong> What is Cloud Computing? <br>
                <strong>1.2 </strong> Cloud Service and Deployment Models <br>
                <strong>1.3 </strong> How AWS is the leader in the cloud domain? <br>
                <strong>1.4 </strong> Various cloud computing products offered by AWS <br>
                <strong>1.5 </strong> Introduction to AWS S3, EC2, VPC, EBS, ELB, AMI <br>
                <strong>1.6 </strong> AWS architecture and the AWS Management Console, virtualization in AWS
                (Xen
                hypervisor) <br>
                <strong>1.7 </strong> What is Auto-scaling? <br>
                <strong>1.8 </strong> AWS EC2 best practices and costs involved. <br>

                <strong>Hands-on Exercise </strong> – Setting up an AWS account, how to launch an EC2
                instance, the
                process of hosting a website, and launching a Linux Virtual Machine using an AWS EC2
                instance. <br><br>
                <div class="text-h6"><strong>Module 02 - Elastic Compute and Storage Volumes</strong></div>
                <br>
                <strong>2.1 </strong> Introduction to EC2 <br>
                <strong>2.2 </strong> Regions and Availability Zones(AZs) <br>
                <strong>2.3 </strong> Pre-EC2, EC2 instance types <br>
                <strong>2.4 </strong> Comparing Public IP and Elastic IP <br>
                <strong>2.5 </strong> Demonstrating how to launch an AWS EC2 instance <br>
                <strong>2.6 </strong> Introduction to AMIs, Creating and Copying an AMI <br>
                <strong>2.7 </strong> Introduction to EBS <br>
                <strong>2.8 </strong> EBS volume types <br>
                <strong>2.9 </strong> EBS Snapshots <br>
                <strong>2.10 </strong> Introduction to EFS <br>
                <strong>2.11 </strong> Instance tenancy- Reserved and Spot instances <br>
                <strong>2.12 </strong> Pricing and Design Patterns. <br>

                <strong>Hands-on Exercise –</strong> <br>
                <strong>1. </strong> Launching an EC2 instance <br>
                <strong>2. </strong> Creating an AMI of the launched instance <br>
                <strong>3. </strong> Copying the AMI to another region <br>
                <strong>4. </strong> Creating an EBS volume <br>
                <strong>5. </strong> Attaching the EBS volume with an instance <br>
                <strong>6. </strong> Taking backup of an EBS volume <br>
                <strong>7. </strong> Creating an EFS volume and mounting the EFS volume to two instances.
                <br><br>

                <div class="text-h6"><strong>Module 03 - Load Balancing, Autoscaling, and DNS</strong></div>
                <br>
                <strong>3.1 </strong> Introduction to Elastic Load Balancer <br>
                <strong>3.2 </strong> Types of ELB – Classic, Network, and Application <br>
                <strong>3.3 </strong> Load balancer architecture <br>
                <strong>3.4 </strong> Cross-zone load balancing <br>
                <strong>3.5 </strong> Introduction to Auto Scaling, vertical and horizontal scaling, the
                lifecycle of
                AutoScaling <br>
                <strong>3.6 </strong> Components of Auto Scaling, scaling options and policy, instance
                termination <br>
                <strong>3.7 </strong> Using load balancer with Auto Scaling <br>
                <strong>3.8 </strong> Pre-Route 53 – How DNS works? <br>
                <strong>3.9 </strong> Routing policy, Route 53 terminologies, Pricing <br>

                <strong>Hands-on Exercise –</strong> <br>
                <strong>1. </strong> Creating a Classic ELB <br>
                <strong>2. </strong> Creating an Application ELB <br>
                <strong>3. </strong> Creating an Auto Scaling group <br>
                <strong>4. </strong> Configuring an Auto Scaling group <br>
                <strong>5. </strong> Integrating ELB with Auto Scaling <br>
                <strong>6. </strong> Redirect traffic from domain name to ELB using Route 53. <br><br>
                <div class="text-h6"><strong>Module 04 - Virtual Private Cloud</strong></div> <br>
                <strong>4.1 </strong> What is Amazon VPC? <br>
                <strong>4.2 </strong> VPC as a networking layer for EC2 <br>
                <strong>4.3 </strong> IP address and CIDR notations <br>
                <strong>4.4 </strong> Components of VPC – Network interfaces, route tables, internet
                gateway, NAT <br>
                <strong>4.5 </strong> Security in VPC – Security groups and NACL, types of VPC, what is a
                subnet, VPC
                peering with
                scenarios, VPC endpoints, VPC pricing, and design patterns <br>
                <strong>Hands-on Exercise –</strong> <br>
                <strong>1. </strong> Creating a VPC and subnets, <br>
                <strong>2. </strong> Creating a 3 Tier architecture with security groups <br>
                <strong>3. </strong> NACL, Internet gateway, and NAT gateway <br>
                <strong>4. </strong> Creating a complete VPC architecture <br><br>
                <div class="text-h6"><strong>Module 05 - Storage - Simple Storage Service (S3)</strong>
                </div> <br>
                <strong>5.1 </strong> Introduction to AWS storage <br>
                <strong>5.2 </strong> Pre-S3 – online cloud storage <br>
                <strong>5.3 </strong> API, S3 consistency models <br>
                <strong>5.4 </strong> Storage hierarchy, buckets in S3 <br>
                <strong>5.5 </strong> Objects in S3, metadata and storage classes, object versioning, object
                lifecycle
                management,
                cross-region replication, data encryption, connecting using VPC endpoint, S3 pricing. <br>

                <strong>Hands-on Exercise –</strong> <br>
                <strong>1. </strong> Creating an S3 bucket <br>
                <strong>2. </strong> Uploading objects to the S3 bucket <br>
                <strong>3. </strong> Enabling object versioning in the S3 bucket <br>
                <strong>4. </strong> Setting up lifecycle management for only a few objects <br>
                <strong>5. </strong> Setting up lifecycle management for all objects with the same tag <br>
                <strong>6. </strong> Static website hosting using S3.
              </q-tab-panel>

              <q-tab-panel name="module6-module10">
                <div class="text-h6"><strong>Module 06 - Databases and In-Memory DataStores</strong></div>
                <br>
                <strong>6.1 </strong> What is a database, types of databases, databases on AWS
                <strong>6.2 </strong> Introduction to Amazon RDS
                <strong>6.3 </strong> Multi-AZ deployments, features of RDS
                <strong>6.4 </strong> Read replicas in RDS, reserved DB instances
                <strong>6.5 </strong> RDS pricing and design patterns
                <strong>6.6 </strong> Introduction to Amazon Aurora, benefits of Aurora, Aurora pricing, and
                design
                patterns
                <strong>6.7 </strong> Introduction to DynamoDB, components of DynamoDB, DynamoDB pricing,
                and design
                patterns
                <strong>6.8 </strong> What is Amazon Redshift, and what are the advantages of Redshift?
                <strong>6.9 </strong> What is ElastiCache, and why ElastiCache?

                <strong>Hands-on Exercise –</strong> <br>
                <strong>1. </strong> Launching a MySQL RDS instance <br>
                <strong>2. </strong> Modifying an RDS instance <br>
                <strong>3. </strong> Connecting to the DB instance from your machine <br>
                <strong>4. </strong> Creating a multi-az deployment <br>
                <strong>5. </strong> Create an Aurora DB cluster <br>
                <strong>6. </strong> Creating an Aurora replica <br>
                <strong>7. </strong> Creating a DynamoDB table. <br><br>
                <div class="text-h6"><strong>Module 07 - Management and Application Services</strong></div>
                <br>
                <strong>7.1 </strong> Introduction to CloudFormation <br>
                <strong>7.2 </strong> CloudFormation components<br>
                <strong>7.3 </strong> CloudFormation templates<br>
                <strong>7.4 </strong> The concept of Infrastructure-as-a-code<br>
                <strong>7.5 </strong> Functions and pseudo parameters<br>
                <strong>7.6 </strong> Introduction to Simple Notification Service, how does SNS work<br>
                <strong>7.7 </strong> Introduction to Simple Email Service, how does SES work<br>
                <strong>7.8 </strong> Introduction to Simple Queue Service, how does SQS work.<br>

                <strong>Hands-on Exercise –</strong> <br>
                <strong>1. </strong> Creating a CloudFormation stack<br>
                <strong>2. </strong> Launching a t2.micro<br>
                <strong>3. </strong> EC2 instance using CloudFormation<br>
                <strong>4. </strong> Using CloudFormation to automate an architectural deployment<br>
                <strong>5. </strong> Creating an SNS topic, creating a subscription within the topic<br>
                <strong>6. </strong> Setting up SES and sending a mail<br>
                <strong>7. </strong> Creating an SQS queue and sending a sample message.<br><br>
                <div class="text-h6"><strong>Module 08 - Access Management and Monitoring Services</strong>
                </div> <br>
                <strong>8.1 </strong> Pre-IAM, why access management <br>
                <strong>8.2 </strong> Amazon Resource Name (ARN), IAM features<br>
                <strong>8.3 </strong> Multi-factor Authentication (MFA) in IAM, JSON<br>
                <strong>8.4 </strong> IAM policies, IAM permissions, IAM roles, identity federation,
                pricing<br>
                <strong>8.5 </strong> Introduction to CloudWatch, metrics and namespaces, CloudWatch
                architecture,
                dashboards in CW, CloudWatch alarms, CloudWatch logs, pricing, and design patterns<br>
                <strong>8.6 </strong> Introduction to CloudTrail, tracking API usage.<br>

                <strong>Hands-on Exercise –</strong> <br>
                <strong>1. </strong>Creating IAM users and a group<br>
                <strong>2. </strong>Creating an IAM policy and attaching it to the group<br>
                <strong>3. </strong>Creating an IAM role<br>
                <strong>4. </strong>Set up MFA for a user<br>
                <strong>5. </strong>Creating a CloudWatch dashboard and adding metrics<br>
                <strong>6. </strong>Create a CloudWatch alarm that triggers according to the CPU Utilization
                of an EC2
                instance<br>
                <strong>7. </strong>Creating a billing alarm<br>
                <strong>6. </strong>Creating a log group<br>
                <strong>7. </strong>Creating a trail.<br><br>
                <div class="text-h6"><strong>Module 09 - Automation and Configuration Management</strong>
                </div> <br>
                <strong>9.1 </strong>What is AWS Lambda?<br>
                <strong>9.2 </strong>How is Lambda different from EC2?<br>
                <strong>9.3 </strong>Benefits and limitations of Lambda<br>
                <strong>9.4 </strong>How does Lambda work?<br>
                <strong>9.5 </strong>Use cases of Lambda, Lambda concepts<br>
                <strong>9.6 </strong>Integrating S3 with Lambda<br>
                <strong>9.7 </strong>What is Elastic Beanstalk, how does Beanstalk work?, Beanstalk
                concepts, Beanstalk
                pricing<br>
                <strong>9.8 </strong>What is Configuration Management?<br>
                <strong>9.9 </strong>What is AWS OpsWorks?, AWS OpsWorks benefits<br>
                <strong>9.10</strong> CloudFormation vs OpsWorks, services in OpsWorks, AWS OpsWorks Stacks,
                OpsWorks
                pricing.<br>

                <strong>Hands-on Exercise –</strong> <br>
                <strong>1. </strong> Creating a Lambda function<br>
                <strong>2. </strong> Setting up Lambda triggers and destinations<br>
                <strong>3. </strong> Creating an Elastic Beanstalk application<br>
                <strong>4. </strong> Uploading a new version of the application to Beanstalk<br>
                <strong>5. </strong> Creating a stack in OpsWorks<br>
                <strong>6. </strong> Launching the instance using OpsWorks and automatically installing the
                application.<br><br>
                <div class="text-h6"><strong>MModule 10 - AWS Migration</strong></div> <br>
                <strong>10.1 </strong> What is Cloud migration? <br>
                <strong>10.2 </strong> Why is migration important? <br>
                <strong>10.3 </strong> Migration process in AWS, the 6 R’s migration strategy <br>
                <strong>10.4 </strong> Virtual machine migration, migrating a local VM onto the AWS cloud
                <br>
                <strong>10.5 </strong> Migrating databases using Database Migration Service (DMS) <br>
                <strong>10.6 </strong> Migrating a local database to RDS <br>
                <strong>10.7 </strong> Migrating an on-premises database server to RDS using DMS, and other
                migration
                services.

              </q-tab-panel>

              <q-tab-panel name="self-paced">
                <div class="text-h6"><strong>Module 11 - Architecting AWS Whitepaper</strong></div><br>
                <strong>11.1 </strong> Important guidelines for creating a well-architected AWS framework
                that is
                resilient and performant<br>
                <strong>11.2 </strong> Designing of fault-tolerant and high-availability architecture<br>
                <strong>11.3 </strong> Resilient storage<br>
                <strong>11.4 </strong> Decoupling mechanism<br>
                <strong>11.5 </strong> Multi-tier architecture solution<br>
                <strong>11.6 </strong> Disaster recovery solution<br>
                <strong>11.7 </strong> Scalable and elastic solutions.<br><br>
                <div class="text-h6"><strong>Module 12 - DevOps on AWS</strong></div><br>
                <strong>12.1 </strong> What is DevOps?<br>
                <strong>12.2 </strong> Introduction to AWS DevOps,<br>
                <strong>12.3 </strong> AWS Developer tools – CodeCommit, CodeBuild, CodeDeploy, and
                CodePipeline,
                integrating GitHub with
                CodePipeline,<br>
                <strong>12.4 </strong> Creating a DevOps lifecycle using AWS DevOps tools.<br><br>
              </q-tab-panel>
            </q-tab-panels>
          </q-card>
        </div>
      </div>
    </section>
    <section>
      <div class="box_general skills q-ma-xl q-pa-xs q-ma-xl q-gutter-xs">
        <div class="main_info_wrapper skills-covered q-gutter-sm">
          <div class="row">
            <div class="col-lg-12">
              <h3 style="font-size: 1.7rem;font-family: 'Times New Roman', Times, serif;text-align: center;"><strong>AWS
                  Training in Madurai, Amazon Web Services Certification Course in Madurai and best AWS Institute
                  classes near me</strong></h3>
              <p style="font-family: 'Times New Roman', Times, serif;font-size: 1.2rem;">EdexTech is the Top AWS Training
                Institute in Madurai. We Provide Best AWS Online Training in Madurai.
                Flexible Timings. Get Placed in MNC's with high Quality Training at Best Price. Affordable Fees. Fully
                Hands-on Training. Interview Preparation. It is a limited period offer. Book your seat soon!</p>
            </div>
          </div>
          <div class="row">
            <div class="col-lg-6"><br><br>
              <p style="font-size: 18px; text-align: center;">
                <b>Have An Queries?<br>Ask our Experts Help me to Choose a Course.</b>
              </p>
              <p style="text-align: center;">
                <q-btn class="text-white bg-primary" fdprocessedid="4czig"><a href="tel:+91-8095570001"
                    style="text-decoration: none;color:white;">Call US: +91
                    8095570001</a></q-btn>
              </p>
            </div>
            <div class="col-lg-6" align="center">
              <img src="../assets/our-experts-support.jpg"
                alt="AWS Training and certification cost in madurai" height="163" width="286">
            </div>
          </div>
        </div>
      </div>
    </section>
    <footer>
      <div class="row">
        <div class="col-12">
          <div class="footer-content text-center">
            <div class="footer-contact">
              <a href="#">Madurai: +91-8099770770</a>
              <a href="#">Salem: +91-8767260270</a>
              <a href="#">Chennai: +91-9707250260</a>
              <a href="#">Trichy: +91-8900250260</a>
              <a href="#"><i class="fa fa-envelope"></i> edextech_it@gmail.com</a>
              <a href="#">2, Annai Therasa Street, Bethaniapuram, Kalavasal,Madurai-625016</a>
            </div>
            <div class="footer_privacy">
              <a href="#" title="Terms &amp; Conditions" target="_blank">Terms &amp; Conditions</a>
              <a href="#" title="Privacy Policy" target="_blank">Privacy Policy</a>
              <a href="#" title="Refund/Cancellation Policy" target="_blank">Refund/Cancellation Policy</a>
              <a href="#" title="Terms of Use" target="_blank">Terms of Use</a>
            </div>
          </div>
        </div>
      </div>
    </footer>
  </q-page>
</template>
<style>

</style>
<script>
import {
  ref
} from 'vue'

export default {
  name: 'IndexPage',
  setup() {
    return {

      search: ref(''),
      slide: ref(1),
      autoplay: ref(true),
      tab: ref('mails'),
      bar2: ref(false),
      enrollnow: [
        {
          img: '/classroom-training.jpg',
          title: 'On-Premise Classroom Training',
          paragraph: 'An On-Premise Classroom Platform is a digital replica of a traditional classroom or training room.'
        },
        {
          img: '/online_training.jpg',
          title: 'Instructor-Led Live, Online Training',
          paragraph: 'A virtual classroom, though is online using digital conferencing, webinar, or learning management system technology to provide everyone access.'
        },
        {
          img: '/self-paced-learning.jpg',
          title: 'Self-Paced Online Training',
          paragraph: 'Self-paced learning means you can learn in your own time and schedule. There is no need to complete the assignments and take the courses at the same time as other learners.'
        }
      ],
      skills: [{
        sk: 'AWS EC2 and Elastic Beanstalk'
      },
      {
        sk: 'Amazon S3'
      },
      {
        sk: 'AWS Lambda'
      },
      {
        sk: 'AWS RDS and DynamoDB'
      },
      {
        sk: 'CloudFormation'
      },
      {
        sk: 'AWS Global Infrastructure'
      },
      {
        sk: 'AWS Well-Architected Framework'
      },
      {
        sk: 'AWS Command Line Interface'
      },
      {
        sk: 'AWS Networking'
      },
      {
        sk: 'Auto-scaling'
      },
      {
        sk: 'AWS Security Services'
      },
      {
        sk: 'AWS Databases'
      },
      {
        sk: 'VPC Networking'
      },
      {
        sk: 'AWS Logging Mechanisms'
      },
      {
        sk: 'AWS Storage Cost Optimization'
      },
      ],
      cards: [{
        icon: 'timer',
        title: 'Real-Time Experts as Trainers',
        desc: 'At EdexTech Institution, You will Learn from the Experts from industry who are Passionate in sharing their Knowledge with Learners. Get Personally Mentored by the Experts.',
        color: '#CDA45E'
      },
      {
        icon: 'laptop_mac',
        title: 'LIVE Project',
        desc: 'Get an Opportunity to work in Real-time Projects that will give you a Deep Experience. Showcase your Project Experience &amp; Increase your chance of getting Hired!',
        color: '#FFE0B2'
      },
      {
        icon: 'school',
        title: 'Certification',
        desc: 'Get Certified by EdexTech Institution. Also, get Equipped to Clear Global Certifications. 72% EdexTech Students appear for Global Certifications and 100% of them Clear it.',
        color: '#FFF59D'
      },
      {
        icon: 'currency_rupee',
        title: 'Affordable Fees',
        desc: 'At EdexTech Institution, Course Fee is not only Affordable, but you have the option to pay it in Installments. Quality Training at an Affordable Price is our Motto.',
        color: '#CDA45E'
      },
      {
        icon: 'autorenew',
        title: 'Flexibility',
        desc: 'At EdexTech Institution, you get Ultimate Flexibility. Classroom or Online Training? Early morning or Late evenings? Weekdays or Weekends? Regular Pace or Fast Track?',
        color: '#FFE0B2'
      },
      {
        icon: 'supervisor_account',
        title: 'Placement Support',
        desc: 'Tie-up &amp; MOU with more than 1500+ Small &amp; Medium Companies to Support you with Opportunities to Kick-Start &amp; Step-up your Career.',
        color: '#FFF59D'
      },
      ],
    }
  },
}
</script>

<style>
.form-area {
  background: #fff;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.5), inset 0 8px 0 #6659B8;
  border-radius: 4px;
}

.para {
  font-size: .5rem;
  font-weight: 500;
  margin-top: -0.5rem;
}

.image-col-content-text .image-col-content-text-last {
  padding-right: 0.4rem;
  height: 2.3rem;
  margin: auto;
}

.image-col-content-text {
  border-right: 0.05rem solid #fff;
}

.image-col-content {
  width: 100%;
  display: flex;
  height: 3.5rem;
  align-items: center;
  background-color: #00345a;
  text-align: center;
  justify-content: space-around;
  color: #fff;
  border-radius: 0.5rem;
  /* margin-top: 1rem; */
  /* margin-left: 2rem; */
  padding-left: 0.3rem;
}

.form-container {
  display: flex;
  height: auto;
  margin: auto;
  width: 100%;
  align-items: center;
  justify-content: center;
}

.image-col h3 {
  color: #000;
  font-weight: 500;
  margin-top: 1.2rem;
  font-size: 1.2rem;
  margin-left: 4rem;
}

.image-col {
  width: 25rem;
  display: flex;
  flex-direction: column;
  text-align: center;
  height: 22rem;
  margin-top: 5rem;
}

.forms select {
  width: 80%;
  border: none;
  height: 2.8rem;
  padding: 0 0.5rem;
  font-size: .8rem;
  border-radius: 0.3rem;
  box-shadow: 0 0.2rem 0.3rem 0.1rem #b4b3b3;
}

.forms input {
  width: 80%;
  border: none;
  height: 2.8rem;
  padding: 0 0.5rem;
  font-size: .8rem;
  border-radius: 0.3rem;
  box-shadow: 0 0.2rem 0.3rem 0.1rem #b4b3b3;
}

.forms {
  width: 85%;
  display: flex;
  margin: 0.1rem auto;
  text-align: center;
  justify-content: space-around;
  align-items: center;
}

.form-content {
  width: 95%;
  display: flex;
  margin: 0.5rem 0;
  text-align: center;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
}

.login {
  width: 100%;
  height: auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  background-color: hsla(0, 0%, 100%, .15);
  border-radius: 1rem;
  box-shadow: 0 0.1rem 0.2rem 0.1rem rgba(0, 0, 0, .25);
  margin-top: -0.5rem;
}

.imagebox:hover .box-header {
  transform: translateX(100%);
}

.imagebox .box-header {
  position: absolute;
  left: 25px;
  right: 20px;
  bottom: 20px;
  padding: 5px 55px 5px 15px;
  min-height: 65px;
  transition: all 0.3s ease-in-out;
  transform: translateX(0);
}

.imagebox .box-header .box-title {
  font-size: 15px;
  font-weight: 600;
  text-transform: capitalize;
  line-height: 1.4;
  margin: 0;
  position: relative;
  color: #fff;
}

.imagebox .box-header:before {
  content: "\f054";
  position: absolute;
  font-family: fontawesome;
  text-align: center;
  line-height: 30px;
  right: 15px;
  top: 20px;
  bottom: 5px;
  width: 30px;
  height: 30px;
  color: #429bf4;
  background-color: #fff;
  text-shadow: 0 1px 1px rgb(0 0 0 / 10%);
  font-weight: 400;
  font-size: 12px;
}

.imagebox .box-header .box-title:after {
  width: 50px;
  height: 3px;
  content: "";
  position: absolute;
  left: 0;
  top: -10px;
}

.imagebox .box-header:after {
  width: 100%;
  height: 100%;
  content: "";
  position: absolute;
  left: 0;
  top: 0;
  z-index: -1;
  background-color: #218af2;
  opacity: 0.85;
}

.imagebox:hover .box-content {
  transform: translateX(0);
  visibility: visible;
  opacity: 1;
}

.imagebox .box-content {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  color: #fff;
  padding: 30px;
  text-shadow: 0 1px 1px rgb(0 0 0 / 20%);
  visibility: hidden;
  transform: translateX(-100%);
  opacity: 0;
  transition: all 0.3s ease-in-out;
}

.imagebox .box-content:after {
  content: "";
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  background-color: #0665c3;
  z-index: -1;
  opacity: 0.9;
}

.box-desc {
  display: flex;
  align-items: center;
  height: 100%;
  text-align: center;
  /* line-height: 23px; */
  flex-direction: column;
  justify-content: center;
}

.imagebox {
  position: relative;
  margin: 10px 0;
  border: 1px solid #e5effb;
  box-shadow: rgba(0, 0, 0, 0.16) 0 1px 4px;
}

.imagebox .box-wrapper {
  overflow: hidden;
  position: relative;
  background: #fff;
}

.skill-items p {
  font-weight: 600;
  font-size: 1rem;
  /* line-height: 20px; */
  color: #000;
  padding: 10px;
  text-align: center;
  border-radius: 5px;
  background: #fff;
  border: 1px solid rgba(114, 157, 245, .2);
}

.skill .skill-items p {
  box-shadow: 0 2px 4px rgba(0, 0, 0, .2), inset 4px 0 0 #6659B8;
}

.skills {
  background: #fff;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.5), inset 0 8px 0 #6659B8;
  border-radius: 4px;
}

.example-row-equal-width .row>div {
  padding: 10px 15px;
  background: rgba(#999, .15);
  border: 1px solid rgba(#999, .2);
}

.row+.row {
  margin-top: 1rem;
}

.row:before {
  display: table;
  content: " ";
}

/* Default styles for cards */
.cards {
  margin-bottom: 20px;
  display: flex;
  flex-wrap: wrap;

}

/* Card styles */
.card {
  display: flex;
  flex-direction: column;
  height: 100%;
  box-shadow: 0.4rem 0.4rem 0.2rem 0.1rem #b9b9b9;
  border: 0.1rem solid #b9b9b9;
}

.card {
  background-color: #fff;
  border-radius: 10px;
  min-height: 270px;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  min-width: 200px;
  max-width: 400px;
  margin: 0 auto;
}
.box_general {
  background-color: #fff;
  border-radius: 5px;
  overflow: hidden;
  margin-bottom: 35px;
  box-shadow: 0 7px 25px 0 rgba(0, 0, 0, .1);
}

.main_info_wrapper {
  padding: 30px;
}
.footer_privacy {
    margin-bottom: 10px;

}
.footer_privacy a {
    font-size: 12px;
    display: inline-block;
    color: #fff;
    font-weight: 800;
    margin: 5px 10px;
    position: relative;
    text-decoration: none;
    line-height: 20px;
}
.footer_privacy a::after {
    content: "";
    background: #fff;
    width: 1px;
    height: 65%;
    display: block;
    position: absolute;
    top: 3px;
    left: -10px;
    /* right: -13px; */
}
footer {
  background: #474747;
  padding: 2rem 0 1rem;
}

.footer-contact a i {
  padding: 0 8px;
}

.footer-contact {
  margin-bottom: 20px;
}

.footer-contact a::after {
  content: "";
  background: #fff;
  width: 1px;
  height: 75%;
  display: block;
  position: absolute;
  top: 3px;
  left: -10px;
}

.footer-contact a {
  font-size: 18px;
  display: inline-block;
  color: #fff;
  font-weight: 800;
  margin: 5px 10px;
  position: relative;
  text-decoration: none;
  line-height: 20px;
}

.fa-envelope:before {
  content: "\f0e0";
}
</style>
