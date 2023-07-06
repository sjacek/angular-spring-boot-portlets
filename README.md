# Angular 8 with Spring boot 2 portlets on Liferay 7.2
Examples for creating secure jsr286 or jsr362 portlets on liferay 7.2 with angular 8 and Spring boot 2.
Every portlet is in wars folder and in modules folder there are the services apis produced by service builder.

## Books catalog example
A basic crud application where only authenticated users of portal can view the stored books on database and can add, update or delete a book of them.

This portlet leverages the power of angular custom elements and the powerful capabilities of Spring Boot with respect on liferay service builder as regards the persistence layer.

<img src=screenshots/authorized.png  alt="Liferay acreenshot with angular portlet"/>

## Download and install the Liferay Portal 7.2 server.
After you have cloned the project, open a terminal to the angular-spring-boot-portlets folder and run

<code>./mvnw bundle-support:init</code>

The above command downloads the Liferay Portal specified in pom.xml version (7.2) from the specified repository

(https://releases-cdn.liferay.com/portal/7.2.0-ga1/liferay-ce-portal-tomcat-7.2.0-ga1-20190531153709761.tar.gz). 

Now you have a complete development environment to  play with this project.  

For more information about setting up a liferay development environment refer to the following links

https://portal.liferay.dev/docs/7-0/reference/-/knowledge_base/r/bundle-support-plugin

https://portal.liferay.dev/docs/7-0/tutorials/-/knowledge_base/t/tooling

## How to build and deploy the modules
1) set JAVA_HOME environment variable to the JDK8 home folder

2) Enable legacy OpenSSL provider.
   https://github.com/webpack/webpack/issues/14532#issuecomment-947012063

    On Unix-like (Linux, macOS, Git bash, etc.):
    <code>export NODE_OPTIONS=--openssl-legacy-provider</code>
    
    On Windows command prompt:
    <code>set NODE_OPTIONS=--openssl-legacy-provider</code>

    On PowerShell:
    <code>$env:NODE_OPTIONS = "--openssl-legacy-provider"</code>

3) Install the npm dependencies to angular app by running <br/>
<code>npm install --prefix wars/books-catalog-portlet</code>

4) Run <code>npm run build:portlet --prefix wars/books-catalog-portlet</code>

5) Run <code>./mvnw install</code>

6) Run <code>./mvnw verify</code>
