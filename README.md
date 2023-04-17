# Spring Eureka Server

Spring Cloud Gateway - Eureka Server 구현

## Eureka Server Settings

- build 파일 의존성 추가
  ```groovy
  dependencies {
      implementation 'org.springframework.cloud:spring-cloud-starter-netflix-eureka-server'
  }
  ```
  
- main 클래스에 `@EnableEurekaServer` 추가
  ```java
  @SpringBootApplication
  @EnableEurekaServer
  public class DiscoveryApplication {
      public static void main(String[] args) {
          SpringApplication.run(DiscoveryApplication.class, args);
      }
  }
  ```
  
- property 설정 (application.yml)
  ```yaml
  server:
    port: 8761
  
  spring:
    application:
      name: discovery-service
  
  eureka:
    client:
      register-with-eureka: false # eureka server를 registry에 등록할지
      fetch-registry: false       # registry에 있는 정보들을 가져올지
  ```
