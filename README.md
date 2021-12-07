# Nexus-Repository-Manager-Configs

### Start application
```bash
docker-compose up -d
```

*Application will be up at port: `8081`*
<br/>
<br/>

### First login
> Default user is `admin`, and to show default password run the command:
```bash
docker exec -ti nexus cat /nexus-data/admin.password
```

### Set Npm Registry `.npmrc`
```bash
npm config set registry http://localhost:8081/repository/npmgroup
```
> Group created before in Nexus Panel, with libs.

<br/>
<br/>

### Publish libs
```bash
npm login --registry http://localhost:8081/repository/librs-test-321/
npm publish
```

### Install libs
```bash
npm login --registry http://localhost:8081/repository/npmgroup/
npm install librs-test-321
```

### References
> https://guides.sonatype.com/repo3/quick-start-guides/proxying-maven-and-npm/

> https://help.sonatype.com/repomanager3/formats/npm-registry

> https://hub.docker.com/r/sonatype/nexus3/