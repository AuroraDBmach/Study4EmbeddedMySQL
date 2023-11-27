## Embedded MySQL 개발 방법

#### Embedded MySQL의 정의

특정 응용 프로그램에서 MySQL ecosystem이 제공하는 embedded MySQL library를 이용하여, MySQL 엔진의 기능을 내장하여 응용프로그램의 기능의 일부로 제공하는 것 

##### Embedded MySQL 라이브러리 버전

Embedded MySQL을 지원하는 MySQL 에코시스템은 여러 종이 있으나, 본 사이트에서는 MariaDB 10.9를 기반으로 개발하기로 한다. 다른 에코시스템이 제공하는 라이브러리를 사용할 수도 있을 것이나, 현재(2022년 3월)는 고려하지 않도록 하겠다.

##### 개발 플랫폼

MySQL은 다양한 운영체제와 운영환경을 지원한다. 그러나, 본 사이트에서는 Ubuntu 20.04를 기본 지원 플랫폼으로 제한하도록 하겠다. 다른 환경으로도 어려움 없이 포팅이 가능할 것으로 여겨진다.

##### 사용용도

다양한 응용프로그램을 만들 수 있을 것이지만, 본 프로젝트에서는 시계열 로그 데이터를 고성능으로 인덱싱 및 병렬 쿼리하는 고성능 대용량  관계형 스토리지 엔진을 개발하기로 하겠다. 

##### 키워드

시계열 데이터, 로그 데이터, 병렬 쿼리, 고성능, 대용량 DB, 관계형 데이터베이스, 스토리지 엔진, MySQL, 내장형 MySQL

time series data, log data, parallel query, high performance, VLDB(Veri Large Database), relational DB, Storage Engine, MySQL, Embedded MySQL

------

#### MySQL Ecosystem 

MySQL은 오픈 소스 형태로, 2008년 썬 마이크로시스템에 인수되었었다. 오픈 소스에 부정적 견해이던(?) 오라클에  2010년 인수되었고, 이후, 현재까지 오라클(Oracle)에서 관리하고 있다. MySQL을 오라클이 인수합병하기 전에 (오픈 소스 버전 5.5이던 즈음에) 다양한 브랜치가 만들어져 여러 곳에서 제각각 발전해 오고 있다. 이러한 MySQL 호환 프로그램/프로젝트들을 MySQL 생태계(Ecosystem)이라고 한다.   대표적인 Ecosystem에는 MariaDB, Percona 가 있으며, Facebook MySQL을 비롯한 다양한 버전이 존재하고 있다. 

MySQL Ecosystem들은 MySQL 버전 5.5에서 브랜치가 만들어졌으므로, 5.5버전까지는 소스코드와 기능에서 동일한 기능을 갖는다. 이후, 각 ecosystem들은 각자 버전과 관리체계를 가지며, 심지어, 내부 기능을 달리하며 발전하고 있는 상황이다.

* MariaDB, Percona 등은 MySQL 5.5버전까지는 동일한 사양을 가지지만, 오라클 감독하에 출시된 MySQl 5.6 과 비슷한 시기의 MariaDB 10.X버전 및 Percona 5.6버전 등이 출시되었고, HA(고가용성 구현)은 상호 호환되지 않고, 일부 관리도구등에서도 차이를 보이고 있으나, 근간은 호환되는 부분이 많은 편이다.

#### MariaDB

MySQL 5.5버전에서 브랜치하여 버전을 MariaDB 10.0으로 개칭하여 출발하였다. 이후, 지속적인 발전을 거듭하여, 현재, 버전 10.9에 이르렀다. MySQL 5.5버전과는 완벽하게 호환되지만, HA(고가용성 구현)이 이뤄지는 5.6 버전과는 호환되지 않는다. 별도의 방식으로 HA를 구현하였고, 독자적으로  발전하고 있다.





