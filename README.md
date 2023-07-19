
# Mulesoft Custom Policies
### Introduction
Mulesoft Policies can enforces security using whitelisting or blacklisting IPs/CIDR ranges, traffic contoll using SLA, authentication and threat protrctions etc. Custome policies are Out-Of the Box polcies and can anyone implemente to enhance existing or new functionalities based on the use cases.

Below are Custom Policy process flow,
1. Creation of Custome policy uisng maven archetype
2. Implementation of policy
3. Packahging a policy
4. Deploy or publishing a polciy to exchange
5. Applying policy to APIs through API manager

## Setting up a maven archetype

 First step to setting up a maven archetype to create specified files which required for custom polciy creation. Configure below Mavne Architype in *settings.xml* file

 ```http
 <profiles>
   <profile>
     <id>archetype-repository</id>
     <repositories>
       <repository>
         <id>archetype</id>
         <name>Mule Repository</name>
         <url>https://repository.mulesoft.org/nexus/content/repositories/public</url>
         <releases>
           <enabled>true</enabled>
           <checksumPolicy>fail</checksumPolicy>
         </releases>
         <snapshots>
           <enabled>true</enabled>
           <checksumPolicy>warn</checksumPolicy>
         </snapshots>
       </repository>
     </repositories>
   </profile>
 </profiles> 
 ```
## Project settup using archetyp

After Maven confoguration, execute below maven command to create a custom polciy with default files
 ```http
mvn -Parchetype-repository archetype:generate -DarchetypeGroupId=org.mule.tools -DarchetypeArtifactId=api-gateway-custom-policy-archetype -DarchetypeVersion=1.2.0 -DgroupId=${groupId} -DartifactId=${polciyname} -Dversion=1.0.0-SNAPSHOT -Dpackage=mule-policy
```
Here,
 1. {groupId} is nothing but organization gorup id from anypoint cloudhub where policy to deploy
 2. {policyName} name of the polciy for the desired functionality.




## Acknowledgements

 - [MuleSoft Custom Polcies Overview](https://docs.mulesoft.com/mule-gateway/policies-custom-overview)


## Documentation

[Documentation](https://linktodocumentation)

