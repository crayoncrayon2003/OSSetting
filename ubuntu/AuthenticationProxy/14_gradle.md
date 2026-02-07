# gradle
## gradle.properties
```bash
mkdir -p ~/.gradle
vim ~/.gradle/gradle.properties
```

```properties
systemProp.http.proxyHost=ProxyIP
systemProp.http.proxyPort=ProxyPort
systemProp.http.proxyUser=user
systemProp.http.proxyPassword=pass

systemProp.https.proxyHost=ProxyIP
systemProp.https.proxyPort=ProxyPort
systemProp.https.proxyUser=user
systemProp.https.proxyPassword=pass
```

## Environment Variables
```bash
vim ~/.bashrc
```

```
export GRADLE_OPTS="-Dhttp.proxyHost=ProxyIP -Dhttp.proxyPort=ProxyPort -Dhttp.proxyUser=user -Dhttp.proxyPassword=pass -Dhttps.proxyHost=ProxyIP -Dhttps.proxyPort=ProxyPort -Dhttps.proxyUser=user -Dhttps.proxyPassword=pass"
```

```bash
source ~/.bashrc
```

## Gradle Wrapper download URL
Change the Gradle Wrapper download URL

```bash
vim gradle/wrapper/gradle-wrapper.properties
```

Before
```properties
distributionBase=GRADLE_USER_HOME
distributionPath=wrapper/dists
distributionUrl=https\://services.gradle.org/distributions/gradle-8.2.1-all.zip
networkTimeout=10000
validateDistributionUrl=true
zipStoreBase=GRADLE_USER_HOME
zipStorePath=wrapper/dists
```

After ( https -> http )
```properties
distributionBase=GRADLE_USER_HOME
distributionPath=wrapper/dists
distributionUrl=http\://services.gradle.org/distributions/gradle-8.2.1-all.zip
networkTimeout=10000
validateDistributionUrl=true
zipStoreBase=GRADLE_USER_HOME
zipStorePath=wrapper/dists
```

## Exec
### case1
```bash
./gradlew clean
```

### case2
Download the package manually

```bash
mkdir -p ~/.gradle/wrapper/dists/gradle-8.2.1-all/16f119zgmyuloex46vr4p0coj
curl -x http://user:pass@ProxyIP:ProxyPort \
  -L https://services.gradle.org/distributions/gradle-8.2.1-all.zip \
  -o ~/.gradle/wrapper/dists/gradle-8.2.1-all/16f119zgmyuloex46vr4p0coj/gradle-8.2.1-all.zip
```

```bash
./gradlew clean
```