# **JPA** ๐

### ์ฐธ๊ณ ์๋ฃ

- ์๋ฐ ORM ํ์ค JPA ํ๋ก๊ทธ๋๋ฐ (๊น์ํ ์ )

### ํ์ต ํ๋ก์ ํธ ์ ์ฅ์

- [๋งํฌ]()

## ๋ชฉ์ฐจ
>- [JPA ์๊ฐ](#jpa-์๊ฐ)
>>- [SQL์ ์ง์  ๋ค๋ฃฐ ๋ ๋ฐ์ํ๋ ๋ฌธ์ ์ ](#sql์-์ง์ -๋ค๋ฃฐ-๋-๋ฐ์ํ๋-๋ฌธ์ ์ )
>>- [ํจ๋ฌ๋ค์์ ๋ถ์ผ์น](#ํจ๋ฌ๋ค์์-๋ถ์ผ์น)
>>- [JPA๋ ๋ฌด์์ธ๊ฐ?](#jpa๋-๋ฌด์์ธ๊ฐ)
>- [JPA ์์](#jpa-์์)
>>- [๋ผ์ด๋ธ๋ฌ๋ฆฌ์ ํ๋ก์ ํธ ๊ตฌ์กฐ](#๋ผ์ด๋ธ๋ฌ๋ฆฌ์-ํ๋ก์ ํธ-๊ตฌ์กฐ)
>>- [๊ฐ์ฒด ๋งคํ ์์](#๊ฐ์ฒด-๋งคํ-์์)
>>- [persistence.xml ์ค์ ](#persistencexml-์ค์ )
>>- [์ ํ๋ฆฌ์ผ์ด์ ๊ฐ๋ฐ](#์ ํ๋ฆฌ์ผ์ด์-๊ฐ๋ฐ)
>- [์์์ฑ ๊ด๋ฆฌ](#์์์ฑ-๊ด๋ฆฌ)


<br>

---

## JPA ์๊ฐ

>### SQL์ ์ง์  ๋ค๋ฃฐ ๋ ๋ฐ์ํ๋ ๋ฌธ์ ์ 
>- ๋ฐ๋ณต, ๋ฐ๋ณต ๊ทธ๋ฆฌ๊ณ  ๋ฐ๋ณต
>>- DB๋ ๊ฐ์ฒด ๊ตฌ์กฐ์๋ ๋ค๋ฅด๊ฒ ๋ฐ์ดํฐ ์ค์ฌ์ ๊ตฌ์กฐ๋ฅผ ๊ฐ์ง๋ฏ๋ก ๊ฐ์ฒด๋ฅผ DB์ ์ง์  ์ ์ฅํ๊ฑฐ๋ ์กฐํํ  ์ ์์
>>- ๊ฐ๋ฐ์๊ฐ ๊ฐ์ฒด์งํฅ ์ ํ๋ฆฌ์ผ์ด์๊ณผ DB ์ค๊ฐ์์ SQL๊ณผ JDBC API๋ฅผ ์ฌ์ฉํ์ฌ ๋ณํ ์์์ ์ง์  ํด์ฃผ์ด์ผ ํจ
>>- ๊ฐ์ฒด๋ฅผ DB์ CRUDํ๋ ค๋ฉด ๋ง์ SQL๊ณผ JDBC API๋ฅผ ์ฝ๋๋ก ์์ฑํด์ผ ํ๋ฉฐ ํ์ด๋ธ๋ง๋ค ๋ฐ๋ณตํด์ผ ํ๋ฏ๋ก ๋ฐ์ดํฐ ์ ๊ทผ ๊ณ์ธต (DAO) ๊ฐ๋ฐ์ ๋ง์ ์๊ฐ์ ๋ญ๋นํ๊ฒ๋จ
>- SQL์ ์์กด์ ์ธ ๊ฐ๋ฐ
>>- ๊ฐ์ฒด์ ์ฐ๊ด๋ ๊ฐ์ฒด๋ฅผ ์ฌ์ฉํ  ์ ์์์ง ์์์ง๋ ์ ์ ์ผ๋ก ์ฌ์ฉํ๋ SQL์ ๋ฌ๋ ค์์ผ๋ฏ๋ก DAO๋ฅผ ์ฌ์ฉํ์ฌ SQL์ ์จ๊ฒจ๋ ๊ฒฐ๊ตญ DAO๋ฅผ ์ด์ด์ ์ด๋ค SQL์ด ์คํ๋๋์ง ํ์ธํด์ผ ํ๋ค๋ ๋ฌธ์ ์ ์ด ์์
>>- ๋น์ฆ๋์ค ์๊ตฌ์ฌํญ์ ๋ชจ๋ธ๋งํ ๊ฐ์ฒด๋ฅผ ์ํฐํฐ๋ผ๊ณ  ํ๋๋ฐ, SQL์ ๋ชจ๋  ๊ฒ์ ์์กดํ๋ ์ํฉ์์๋ ๊ฐ๋ฐ์๋ค์ด ์ํฐํฐ๋ฅผ ์ ๋ขฐํ๊ณ  ์ฌ์ฉํ  ์ ์๊ณ  DAO๋ฅผ ์ด์ด์ ์ผ์ผํ ํ์ธํด์ผ ํจ
>>- ๋ฌผ๋ฆฌ์ ์ผ๋ก SQL๊ณผ JDBC API๋ฅผ DAO์ ์จ๊ธฐ๋ ๋ฐ ์ฑ๊ณตํ์ง๋ง ๋ผ๋ฆฌ์ ์ผ๋ก ์ํฐํฐ์ ์์ฃผ ๊ฐํ ์์กด๊ด๊ณ๋ฅผ ๊ฐ์ง๊ณ  ์์ผ๋ฏ๋ก ์ง์ ํ ์๋ฏธ์ ๊ณ์ธต ๋ถํ ์ด ์๋
>>- ๊ฐํ ์์กด ๊ด๊ณ ๋๋ฌธ์ ์กฐํํ  ๋๋ ํ๋๋ฅผ ์ถ๊ฐํ  ๋๋ DAO์ CRUD ์ฝ๋์ SQL ๋๋ถ๋ถ์ ๋ณ๊ฒฝํด์ผ ํ๋ ๋ฌธ์ ๊ฐ ๋ฐ์ํจ
>- JPA์ ๋ฌธ์  ํด๊ฒฐ
>>- JPA๋ฅผ ์ฌ์ฉํ๋ฉด ๊ฐ์ฒด๋ฅผ DB์ ์ ์ฅํ๊ณ  ๊ด๋ฆฌํ  ๋, ๊ฐ๋ฐ์๊ฐ ์ง์  SQL์ ์์ฑํ๋ ๊ฒ์ด ์๋๋ผ JPA๊ฐ ์ ๊ณตํ๋ API๋ฅผ ์ฌ์ฉํ๊ณ , JPA๊ฐ ๊ฐ๋ฐ์ ๋์  SQL์ ์์ฑํด์ DB์ ์ ๋ฌํจ
>>- JPA๊ฐ ์ ๊ณตํ๋ CRUD API
>>>- ์ ์ฅ ๊ธฐ๋ฅ
>>>>```java
>>>>jpa.persist(member);
>>>>```
>>>>- ํธ์ถ์ JPA๊ฐ ๊ฐ์ฒด์ ๋งคํ์ ๋ณด๋ฅผ ๋ณด๊ณ  ์ ์ ํ INSERT SQL์ ์์ฑํด์ DB์ ์ ๋ฌํจ
>>>- ์กฐํ ๊ธฐ๋ฅ
>>>>```java
>>>>String memberId = "helloId";
>>>>Member member = jpa.find(Member.class, memberId);
>>>>```
>>>>- ํธ์ถ์ JPA๊ฐ ๊ฐ์ฒด์ ๋งคํ์ ๋ณด๋ฅผ ๋ณด๊ณ  ์ ์ ํ SELECT SQL์ ์์ฑํด์ DB์ ์ ๋ฌํ๊ณ  ๊ทธ ๊ฒฐ๊ณผ๋ก Member ๊ฐ์ฒด๋ฅผ ์์ฑํด์ ๋ฐํํจ
>>>- ์์  ๊ธฐ๋ฅ
>>>>```java
>>>>Member member = jpa.find(Member.class, memberId);
>>>>member.setName("์ด๋ฆ๋ณ๊ฒฝ");
>>>>```
>>>>- JPA๋ ๋ณ๋์ ์์  ๋ฉ์๋๋ฅผ ์ ๊ณตํ์ง ์๋ ๋์  ๊ฐ์ฒด๋ฅผ ์กฐํํด์ ๊ฐ์ ๋ณ๊ฒฝํ๋ฉด ํธ๋์ญ์์ ์ปค๋ฐํ  ๋ DB์ ์ ์ ํ UPDATE SQL์ด ์ ๋ฌ๋จ
>>>- ์ฐ๊ด๋ ๊ฐ์ฒด ์กฐํ
>>>>```java
>>>>Member member = jpa.find(Member.class, memberId);
>>>>Team team = member.getTeam();
>>>>```
>>>>- JPA๋ ์ฐ๊ด๋ ๊ฐ์ฒด๋ฅผ ์ฌ์ฉํ๋ ์์ ์ ์ ์ ํ SELECT SQL์ ์คํํ๋ฏ๋ก, JPA๋ฅผ ์ฌ์ฉํ๋ฉด ์ฐ๊ด๋ ๊ฐ์ฒด๋ฅผ ๋ง์๊ป ์กฐํํ  ์ ์์

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

>### ํจ๋ฌ๋ค์์ ๋ถ์ผ์น
>- ์์
>>- ๊ฐ์ฒด๋ ์์์ด๋ผ๋ ๊ธฐ๋ฅ์ ๊ฐ์ง๊ณ  ์์ง๋ง ํ์ด๋ธ์ ์์์ด๋ผ๋ ๊ธฐ๋ฅ์ด ์์
>>- DB ๋ชจ๋ธ๋ง์ ์ํผํ์, ์๋ธํ์ ๊ด๊ณ๋ฅผ ์ฌ์ฉํ๋ฉด ๊ทธ๋๋ง ๊ฐ์ฒด ์์๊ณผ ๊ฐ์ฅ ์ ์ฌํ ํํ๋ก ํ์ด๋ธ์ ์ค๊ณํ  ์ ์์
>>- ๊ฐ์ฒด ๋ชจ๋ธ ์ฝ๋
>>>```java
>>>abstract class Item {
>>>  Long id;
>>>  String name;
>>>  int price;
>>>}
>>>
>>>class Album extends Item {
>>>  String artist;
>>>}
>>>
>>>class Movie extends Item {
>>>  String director;
>>>  String actor;
>>>}
>>>
>>>class Book extends Item {
>>>  String author;
>>>  String isbn;
>>>}
>>>```
>>- ํจ๋ฌ๋ค์ ๋ถ์ผ์น๋ฅผ ํด๊ฒฐํ๊ธฐ ์ํด ์๋ชจํ๋ ๋น์ฉ
>>>- ์ ์ฝ๋์์ ํ๋์ ๊ฐ์ฒด๋ฅผ ์ ์ฅํ๋ ค๋ฉด ๊ฐ์ฒด๋ฅผ ๋ถํดํด์ ๋ ๊ฐ์ SQL์ ๋ง๋ค์ด์ผ ํจ
>>>>```sql
>>>>INSERT INTO ITEAM ...
>>>>INSERT INTO ALBUM ...
>>>>```
>>>- JDBC API๋ก ์ฝ๋๋ฅผ ์์ฑํ๋ ค๋ฉด ๋ถ๋ชจ ๊ฐ์ฒด์์ ๋ถ๋ชจ ๋ฐ์ดํฐ๋ง ๊บผ๋ด์ ITEM์ฉ INSERT SQL์ ์์ฑํ๊ณ , ์์ ๊ฐ์ฒด์์ ์์ ๋ฐ์ดํฐ๋ง ๊บผ๋ด์ ALBUM์ฉ INSERT SQL์ ์์ฑํด์ผํ๋ฉฐ, ์์ ํ์์ ๋ฐ๋ผ DTYPE๋ ์ ์ฅํด์ผ ํ๋ ๋ฑ ์ฝ๋๋์ด ๋ง๋ง์น ์์
>>>- ์กฐํํ  ๋๋, ITEM๊ณผ ALBUM ํ์ด๋ธ์ ์กฐ์ธ ํ ์กฐํํ์ฌ ๊ทธ ๊ฒฐ๊ณผ๋ก Album ๊ฐ์ฒด๋ฅผ ์์ฑํด์ผ ํจ
>>>- ๋ง์ฝ ํด๋น ๊ฐ์ฒด๋ค์ DB๊ฐ ์๋ ์๋ฐ ์ปฌ๋ ์์ ๋ณด๊ดํ๋ค๋ฉด ํ์์ ๋ํ ๊ณ ๋ฏผ ์์ด ํด๋น ์ปฌ๋ ์์ ๊ทธ๋ฅ ์ฌ์ฉํ๋ฉด ๋จ
>>>>```java
>>>>list.add(album);
>>>>list.add(movie);
>>>>
>>>>Album album=list.get(albumId);
>>>>```
>>- JPA์ ์์
>>>- JPA๋ ์์๊ณผ ๊ด๋ จ๋ ํจ๋ฌ๋ค์์ ๋ถ์ผ์น ๋ฌธ์ ๋ฅผ ๊ฐ๋ฐ์ ๋์  ํด๊ฒฐํด ์ฃผ๊ธฐ ๋๋ฌธ์ ๊ฐ๋ฐ์๋ ์๋ฐ ์ปฌ๋ ์์ ๊ฐ์ฒด๋ฅผ ์ ์ฅํ๋ฏ์ด JPA์๊ฒ ๊ฐ์ฒด๋ฅผ ์ ์ฅํ๋ฉด ๋จ
>>>- JPA๋ฅผ ์ฌ์ฉํ์ฌ Item์ ์์ํ Album ๊ฐ์ฒด๋ฅผ ์ ์ฅํ๋ ๊ณผ์  ์์
>>>>```java
>>>>jpa.persist(album);
>>>>```
>>>>- persist() ๋ฉ์๋๋ฅผ ์ฌ์ฉํ์ฌ ๊ฐ์ฒด๋ฅผ ์ ์ฅํ๋ฉด JPA๋ ๋ ๊ฐ์ SQL์ ์คํํด์ ๊ฐ์ฒด๋ฅผ ITEM, ALBUM ๋ ํ์ด๋ธ์ ๋๋์ด ์ ์ฅํจ
>>>>>```sql
>>>>>INSERT INTO ITEAM ...
>>>>>INSERT INTO ALBUM ...
>>>>>```
>>>- JPA๋ฅผ ์ฌ์ฉํ์ฌ Album ๊ฐ์ฒด๋ฅผ ์กฐํํ๋ ๊ณผ์  ์์
>>>>```java
>>>>String albumId="id100";
>>>>Album album=jpa.find(Album.class, albumId);
>>>>```
>>>>- JPA๋ ITEM๊ณผ ALBUM ๋ ํ์ด๋ธ์ ์กฐ์ธํด์ ํ์ํ ๋ฐ์ดํฐ๋ฅผ ์กฐํํ๊ณ  ๊ทธ ๊ฒฐ๊ณผ๋ฅผ ๋ฐํํจ
>>>>>```sql
>>>>>SELECT I.*, A.*
>>>>>  FROM ITEM I
>>>>>  JOIN ALBUM A ON I.ITEM_ID = A.ITEM_ID
>>>>>```
>- ์ฐ๊ด๊ด๊ณ
>>- ๊ฐ์
>>>- ๊ฐ์ฒด๋ ์ฐธ์กฐ๋ฅผ ์ฌ์ฉํ์ฌ ๋ค๋ฅธ ๊ฐ์ฒด์ ์ฐ๊ด๊ด๊ณ๋ฅผ ๊ฐ์ง๋ฉฐ ์ฐธ์กฐ์ ์ ๊ทผํด์ ์ฐ๊ด๋ ๊ฐ์ฒด๋ฅผ ์กฐํ, ๋ฐ๋ฉด์ ํ์ด๋ธ์ ์ธ๋ ํค๋ฅผ ์ฌ์ฉํด์ ๋ค๋ฅธ ํ์ด๋ธ๊ณผ ์ฐ๊ด๊ด๊ณ๋ฅผ ๊ฐ์ง๋ฉฐ ์กฐ์ธ์ ์ฌ์ฉํด์ ์ฐ๊ด๋ ํ์ด๋ธ์ ์กฐํํจ
>>>- ์ฐธ์กฐ๋ฅผ ์ฌ์ฉํ๋ ๊ฐ์ฒด์ ์ธ๋ ํค๋ฅผ ์ฌ์ฉํ๋ ๊ด๊ณํ DB ์ฌ์ด์ ํจ๋ฌ๋ค์ ๋ถ์ผ์น๋ ๋งค์ฐ ๊ทน๋ณตํ๊ธฐ ์ด๋ ค์ด ๋ฌธ์ ์ ์ด ์์
>>>>- Member ๊ฐ์ฒด๋ Member.team ํ๋์ Team ๊ฐ์ฒด์ ์ฐธ์กฐ๋ฅผ ๋ณด๊ดํ์ฌ Team ๊ฐ์ฒด์ ๊ด๊ณ๋ฅผ ๋งบ๊ณ , team ์ฐธ์กฐ ํ๋์ ์ ๊ทผํ๋ฉด Member์ ์ฐ๊ด๋ Team์ ์กฐํํ  ์ ์์
>>>>- MEMBER ํ์ด๋ธ์ MEMBER.TEAM_ID ์ธ๋ ํค ์ปฌ๋ผ์ ์ฌ์ฉํด์ TEAM ํ์ด๋ธ๊ณผ ๊ด๊ณ๋ฅผ ๋งบ๊ณ , ์ธ๋ ํค๋ฅผ ์ฌ์ฉํด์ ๋ ํ์ด๋ธ์ ์กฐ์ธํ๋ฉด ์ฐ๊ด๋ TEAM ํ์ด๋ธ์ ์กฐํํ  ์ ์์
>>>>- ๋ํ ๊ฐ์ฒด๋ ์ฐธ์กฐ๊ฐ ์๋ ๋ฐฉํฅ์ผ๋ก๋ง ์กฐํํ  ์ ์์ง๋ง ํ์ด๋ธ์ ์๋ฐฉํฅ์ด ๊ฐ๋ฅํจ
>>- ๊ฐ์ฒด๋ฅผ ํ์ด๋ธ์ ๋ง์ถ์ด ๋ชจ๋ธ๋ง
>>>- ํ์ด๋ธ์ ๋ง์ถ ๊ฐ์ฒด ๋ชจ๋ธ
>>>>```java
>>>>class Member {
>>>>  String id;        // MEMBER_ID ์ปฌ๋ผ ์ฌ์ฉ
>>>>  Long teamId;      // TEAM_ID FK ์ปฌ๋ผ ์ฌ์ฉ
>>>>  String username;  // USERNAME ์ปฌ๋ผ ์ฌ์ฉ
>>>>}
>>>>
>>>>class Team {
>>>>  Long id;        // TEAM_ID PK ์ฌ์ฉ
>>>>  String name;    // NAME ์ปฌ๋ผ ์ฌ์ฉ
>>>>}
>>>>```
>>>- ๊ด๊ณํ DB๋ ์กฐ์ธ์ด ์์ผ๋ฏ๋ก ์ธ๋ ํค์ ๊ฐ์ ๊ทธ๋๋ก ๋ณด๊ดํด๋ ๋์ง๋ง ๊ฐ์ฒด๋ ์ฐ๊ด๋ ๊ฐ์ฒด์ ์ฐธ์กฐ๋ฅผ ๋ณด๊ดํด์ผํ๋ฏ๋ก ์กฐํํ  ์ ์์
>>- ๊ฐ์ฒด์งํฅ ๋ชจ๋ธ๋ง
>>>- ์ฐธ์กฐ๋ฅผ ์ฌ์ฉํ๋ ๊ฐ์ฒด ๋ชจ๋ธ
>>>>```java
>>>>class Member {
>>>>  String id;        // MEMBER_ID ์ปฌ๋ผ ์ฌ์ฉ
>>>>  Team team;        // ์ฐธ์กฐ๋ก ์ฐ๊ด๊ด๊ณ๋ฅผ ๋งบ์
>>>>  String username;  // USERNAME ์ปฌ๋ผ ์ฌ์ฉ
>>>>  
>>>>  Team getTeam() {
>>>>    return team;
>>>>  }
>>>>}
>>>>
>>>>class Team {
>>>>  Long id;       // TEAM_ID PK ์ฌ์ฉ
>>>>  String name;   // NAME ์ปฌ๋ผ ์ฌ์ฉ
>>>>}
>>>>```
>>>- ๊ฐ์ฒด์งํฅ ๋ชจ๋ธ๋ง์ ์ฌ์ฉํ๋ฉด ๊ฐ์ฒด๋ฅผ ํ์ด๋ธ์ ์ ์ฅํ๊ฑฐ๋ ์กฐํํ๊ธฐ๊ฐ ์ด๋ ค์
>>>- Member ๊ฐ์ฒด๋ team ํ๋๋ก ์ฐ๊ด๊ด๊ณ๋ฅผ ๋งบ๊ณ  MEMBER ํ์ด๋ธ์ TEAM_ID ์ธ๋ ํค๋ก ์ฐ๊ด๊ด๊ณ๋ฅผ ๋งบ๊ธฐ ๋๋ฌธ์ ๊ฐ์ฒด ๋ชจ๋ธ์ ์ธ๋ ํค๊ฐ ํ์ ์๊ณ  ์ฐธ์กฐ๋ง ์์ผ๋ฉด ๋๋ ๋ฐ๋ฉด์ ํ์ด๋ธ์ ์ฐธ์กฐ๊ฐ ํ์ ์๊ณ  ์ธ๋ ํค๋ง ์์ผ๋ฉด ๋๋ฏ๋ก, ๊ฒฐ๊ตญ ๊ฐ๋ฐ์๊ฐ ์ค๊ฐ์์ ๋ณํ ์ญํ ์ ํด์ผํจ
>>- JPA์ ์ฐ๊ด๊ด๊ณ
>>>```java
>>>member.setTeam(team); // ํ์๊ณผ ํ ์ฐ๊ด๊ด๊ณ ์ค์ 
>>>jpa.persist(member);  // ํ์๊ณผ ์ฐ๊ด๊ด๊ณ ํจ๊ป ์ ์ฅ
>>>```
>>>- JPA๋ team์ ์ฐธ์กฐ๋ฅผ ์ธ๋ ํค๋ก ๋ณํํด์ INSERT SQL์ DB์ ์ ๋ฌํ๊ณ , ๊ฐ์ฒด๋ฅผ ์กฐํํ  ๋ ์ธ๋ ํค๋ฅผ ์ฐธ์กฐ๋ก ๋ณํํ๋ ์ผ๋ JPA๊ฐ ์ฒ๋ฆฌํจ
>>>```java
>>>Member member = jpa.find(Member.class, memberId);
>>>Team team = member.getTeam();
>>>```
>>>- SQL์ ์ง์  ๋ค๋ฃจ์ด๋ ์ด์ฌํ ์ฝ๋๋ง ์์ฑํ๋ฉด ๊ทน๋ณตํ  ์ ์๋ ๋ฌธ์ ๋ก ๋ณด์ผ ์ ์์ผ๋, ์ฐ๊ด๊ด๊ณ์ ๊ด๋ จํ์ฌ ๊ทน๋ณตํ๊ธฐ ์ด๋ ค์ด ํจ๋ฌ๋ค์์ ๋ถ์ผ์น ๋ฌธ์ ๊ฐ ํ์ ๋จ
>- ๊ฐ์ฒด ๊ทธ๋ํ ํ์
>>- ๊ฐ์
>>>- ๊ฐ์ฒด์์ ํ์์ด ์์๋ ํ์ ์กฐํํ  ๋ ์ฐธ์กฐ๋ฅผ ์ฌ์ฉํ์ฌ ์ฐ๊ด๋ ํ์ ์ฐพ๋ ๊ฒ์ ๊ฐ์ฒด ๊ทธ๋ํ ํ์์ด๋ผํจ
>>>- SQL์ ์ง์  ๋ค๋ฃจ๋ฉด ์ฒ์ ์คํํ๋ SQL์ ๋ฐ๋ผ ๊ฐ์ฒด ๊ทธ๋ํ์ ํ์๋ฒ์๊ฐ ์ ํด์ง๋๋ฐ ์ด๊ฒ์ ๊ฐ์ฒด์งํฅ์์  ๋๋ฌด ํฐ ์ ์ฝ์
>>>>- ๋น์ฆ๋์ค ๋ก์ง์ ๋ฐ๋ผ ์ฌ์ฉํ๋ ๊ฐ์ฒด ๊ทธ๋ํ๊ฐ ๋ค๋ฅธ๋ฐ ์ธ์  ๋์ด์ง์ง ๋ชจ๋ฅผ ๊ฐ์ฒด ๊ทธ๋ํ๋ฅผ ํจ๋ถ๋ก ํ์ํ  ์ ์๊ธฐ ๋๋ฌธ
>>>>```java
>>>>class MemberService {
>>>>  ...
>>>>  public void process() {
>>>>    Member member = memberDAO.find(memberId);
>>>>    member.getTeam();  // member->team ๊ฐ์ฒด ๊ทธ๋ํ ํ์์ด ๊ฐ๋ฅํ๊ฐ?
>>>>    member.getOrder().getDelivery(); // ???
>>>>  }
>>>>}
>>>>```
>>>>- MemberService๋ memberDAO๋ฅผ ํตํด member ๊ฐ์ฒด๋ฅผ ์กฐํํ์ง๋ง ์ฐ๊ด๋ Team, Order, Delivery ๋ฐฉํฅ์ผ๋ก ๊ฐ์ฒด ๊ทธ๋ํ๋ฅผ ํ์ํ  ์ ์์์ง ์์์ง ์ฝ๋๋ง ๋ณด๊ณ  ์ ํ ์์ธกํ  ์ ์๊ณ , DAO๋ฅผ ์ด์ด์ SQL์ ์ง์  ํ์ธํด์ผํจ
>>>>- ์ํฐํฐ๊ฐ SQL์ ๋ผ๋ฆฌ์ ์ผ๋ก ์ข์๋์ด ๋ฐ์ํ๋ ๋ฌธ์ ์
>>>>>- ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ๊ณ ์ member์ ์ฐ๊ด๋ ๋ชจ๋  ๊ฐ์ฒด ๊ทธ๋ํ๋ฅผ DB์์ ์กฐํํด์ ์ ํ๋ฆฌ์ผ์ด์ ๋ฉ๋ชจ๋ฆฌ์ ์ฌ๋ ค๋๋ ๊ฒ์ ํ์ค์ฑ์ด ์์
>>>>>- ๊ฒฐ๊ตญ MemberDAO์ ํ์์ ์กฐํํ๋ ๋ฉ์๋๋ฅผ ์ํฉ์ ๋ฐ๋ผ ์ฌ๋ฌ ๋ฒ ๋ง๋ค์ด์ ์ฌ์ฉํด์ผ ํจ
>>>>>```java
>>>>>memberDAO.getMember();
>>>>>memberDAO.getMemberWithTeam();
>>>>>memberDAO.getMemberWithOrderWithDelivery();
>>>>>```
>>- JPA์ ๊ฐ์ฒด ๊ทธ๋ํ ํ์
>>>```java
>>>member.getOrder().getOrderItem()... // ์์ ๋ก์ด ๊ฐ์ฒด ๊ทธ๋ํ ํ์
>>>```
>>>- JPA๋ ์ฐ๊ด๋ ๊ฐ์ฒด๋ฅผ ์ฌ์ฉํ๋ ์์ ์ ์ ์ ํ SQL์ ์คํํ๋ฏ๋ก JPA๋ฅผ ์ฌ์ฉํ๋ฉด ์ฐ๊ด๋ ๊ฐ์ฒด๋ฅผ ์ ๋ขฐํ๊ณ  ๋ง์๊ป ์กฐํํ  ์ ์์
>>>- ํด๋น ๊ธฐ๋ฅ์ ์ค์  ๊ฐ์ฒด๋ฅผ ์ฌ์ฉํ๋ ์์ ๊น์ง DB์กฐํ๋ฅผ ๋ฏธ๋ฃฌ๋ค๊ณ  ํ์ฌ ์ง์ฐ ๋ก๋ฉ์ด๋ผ ํจ
>>>- JPA๋ ์ง์ฐ ๋ก๋ฉ์ ํฌ๋ช(transparent)ํ๊ฒ ์ฒ๋ฆฌํ์ฌ ์ถ๊ฐ์ ์ธ ์ฝ๋๋ฅผ ์์ฑํ  ํ์์์
>>>>```java
>>>>// ์ฒ์ ์กฐํ ์์ ์ SELECT MEMBER SQL
>>>>Member member = jpa.find(Member.class, memberId);
>>>>
>>>>Order order = member.getOrder();
>>>>order.getOrderDate();  // Order๋ฅผ ์ฌ์ฉํ๋ ์์ ์ SELECT ORDER SQL
>>>>```
>>>>- ๋ง์ง๋ง์ค ์ฒ๋ผ ์ค์  Order ๊ฐ์ฒด๋ฅผ ์ฌ์ฉํ๋ ์์ ์ JPA๋ DB์์ ORDER ํ์ด๋ธ์ ์กฐํํ๋ ๊ฒ์ฒ๋ผ ์ง์ฐ ๋ก๋ฉ์ ์ฌ์ฉํจ
>>>>- Member๋ฅผ ์ฌ์ฉํ  ๋๋ง๋ค Order๋ฅผ ํจ๊ป ์ฌ์ฉํ๋ฉด, ํ ํ์ด๋ธ์ฉ ์กฐํํ๊ฒ ๋ณด๋ค Member๋ฅผ ์กฐํํ๋ ์์ ์ SQL ์กฐ์ธ์ ์ฌ์ฉํด์ Member์ Order๋ฅผ ํจ๊ป ์กฐํํ๋๊ฒ์ด ํจ๊ณผ์ ์
>>>- JPA๋ ์ฐ๊ด๋ ๊ฐ์ฒด๋ฅผ ์ฆ์ ํจ๊ป ์กฐํํ ์ง ์๋๋ฉด ์ค์  ์ฌ์ฉ๋๋ ์์ ์ ์ง์ฐํด์ ์กฐํํ ์ง๋ฅผ ๊ฐ๋จํ ์ค์ ์ผ๋ก ์ ์ํ  ์ ์์
>- ๋น๊ต
>>- ๊ฐ์
>>>- DB๋ ๊ธฐ๋ณธ ํค์ ๊ฐ์ผ๋ก ๊ฐ row๋ฅผ ๊ตฌ๋ถํ๋ ๋ฐ๋ฉด์ ๊ฐ์ฒด๋ ๋์ผ์ฑ(identity) ๋น๊ต์ ๋๋ฑ์ฑ(equality) ๋น๊ต๋ผ๋ ๋ ๊ฐ์ง ๋น๊ต ๋ฐฉ๋ฒ์ด ์์
>>>>- ๋์ผ์ฑ ๋น๊ต๋ == ๋น๊ต, ๊ฐ์ฒด ์ธ์คํด์ค์ ์ฃผ์ ๊ฐ์ ๋น๊ตํจ
>>>>- ๋๋ฑ์ฑ ๋น๊ต๋ equlas() ๋ฉ์๋๋ก ๊ฐ์ฒด ๋ด๋ถ์ ๊ฐ์ ๋น๊ตํจ
>>>```java
>>>class MemberDAO {
>>>  public Member getMember(String memberId) {
>>>    String sql = "SELECT * FROM MEMBER WHERE MEMBER_ID = ?";
>>>    ...
>>>    // JDBC API, SQL ์คํ
>>>    return new Member(...);
>>>  }
>>>}
>>>
>>>String memberId = "100";
>>>Member member1 = memberDAO.getMember(memberId);
>>>Member member2 = memberDAO.getMember(memberId);
>>>
>>>member1 == member2; // ๋ค๋ฅด๋ค
>>>```
>>>- ๊ฐ์ ํ์ ๊ฐ์ฒด๋ฅผ ๋ ๋ฒ ์กฐํํ์ง๋ง ๊ฐ์ฒด ์ธก๋ฉด์์ ๋ณผ ๋ ๋์ ๋ค๋ฅธ ์ธ์คํด์ค ์ด๊ธฐ ๋๋ฌธ์ false๊ฐ ๋ฐํ๋จ
>>>```java
>>>Member member1 = list.get(0);
>>>Member member2 = list.get(0);
>>>member1 == member2 // ๊ฐ๋ค
>>>```
>>>- ์ปฌ๋ ์์ ์ ์ฅํ๋ค๋ฉด ๋์ผ์ฑ ๋น๊ต์ ์ฑ๊ณตํจ
>>>- ํจ๋ฌ๋ค์ ๋ถ์ผ์น ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ๊ธฐ ์ํด DB์ ๊ฐ์ row๋ฅผ ์กฐํํ  ๋๋ง๋ค ๊ฐ์ ์ธ์คํด์ค๋ฅผ ๋ฐํํ๋๋ก ๊ตฌํํ๋ ๊ฒ์ ์ฝ์ง ์์ผ๋ฉฐ, ์ฌ๋ฌ ํธ๋์ญ์์ด ๋์์ ์คํ๋๋ ์ํฉ๊น์ง ๊ณ ๋ คํ๋ค๋ฉด ๋์ฑ ์ด๋ ค์์ง
>>- JPA์ ๋น๊ต
>>>- JPA๋ ๊ฐ์ ํธ๋์ญ์์ผ ๋ ๊ฐ์ ๊ฐ์ฒด๊ฐ ์กฐํ๋๋ ๊ฒ์ ๋ณด์ฅํจ
>>>```java
>>>String memberId = "100";
>>>Member member1 = jpa.find(Member.class, memberId);
>>>Member member2 = jpa.find(Member.class, memberId);
>>>member1 == member2; // ๊ฐ์
>>>```
>- ์ ๋ฆฌ
>>- ๊ฐ์ฒด ๋ชจ๋ธ๊ณผ ๊ด๊ณ DB ๋ชจ๋ธ์ ์งํฅํ๋ ํจ๋ฌ๋ค์์ด ์๋ก ๋ฌ๋ผ์, ์ฐจ์ด๋ฅผ ๊ทน๋ณตํ๋ ค๊ณ  ๊ฐ๋ฐ์๊ฐ ๋๋ฌด ๋ง์ ์๊ฐ๊ณผ ์ฝ๋๋ฅผ ์๋นํ๋ค๋ ์ ์ด ๋ฌธ์ ์
>>- ๊ฐ์ฒด์งํฅ ์ดํ๋ฆฌ์ผ์ด์๋ต๊ฒ ์ ๊ตํ ๊ฐ์ฒด ๋ชจ๋ธ๋ง์ ํ ์๋ก ํจ๋ฌ๋ค์ ๋ฌธ์ ๊ฐ ๋ ์ปค์ง๋ค๋ ๋ ํฐ ๋ฌธ์ ๊ฐ ์๊ณ  ํ์ ๋ฉ์ฐ๊ธฐ ์ํด ๊ฐ๋ฐ์๊ฐ ์๋ชจํด์ผ ํ๋ ๋น์ฉ๋ ์ ์  ๋ ๋ง์์ง๋ฉฐ, ๊ฒฐ๊ตญ ๊ฐ์ฒด ๋ชจ๋ธ๋ง์ ํ์ ์๊ณ  ์ ์  ๋ฐ์ดํฐ ์ค์ฌ์ ๋ชจ๋ธ๋ก ๋ณํด๊ฐ
>>- ์๋ฐ ์ง์์์ ์ค๋ ๊ธฐ๊ฐ ํจ๋ฌ๋ค์ ๋ถ์ผ์น ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ๊ธฐ ์ํด ๋ง์ ๋ธ๋ ฅ์ ๊ธฐ์ธ์ฌ์จ ๊ฒฐ๊ณผ๋ฌผ์ด JPA์ด๋ฉฐ, JPA๋ ํจ๋ฌ๋ค์ ๋ถ์ผ์น ๋ฌธ์ ๋ฅผ ํด๊ฒฐํด์ฃผ๊ณ  ์ ๊ตํ ๊ฐ์ฒด ๋ชจ๋ธ๋ง์ ์ ์งํ๊ฒ ๋์์ค

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

>### JPA๋ ๋ฌด์์ธ๊ฐ?
>- ๊ฐ์
>>- JPA(Java Persistence API)๋ ์๋ฐ ์ง์์ ORM ๊ธฐ์  ํ์ค์ด๋ฉฐ, ์ ํ๋ฆฌ์ผ์ด์๊ณผ JDBC ์ฌ์ด์์ ๋์ํจ
>>- ORM(Object-Relational Mapping)์ ๊ฐ์ฒด์ ๊ด๊ณํ DB๋ฅผ ๋งคํํ๋ค๋ ์๋ฏธ
>>- ORM ํ๋ ์์ํฌ๋ ๊ฐ์ฒด์ ํ์ด๋ธ์ ๋งคํํด์ ํจ๋ฌ๋ค์์ ๋ถ์ผ์น ๋ฌธ์ ๋ฅผ ๊ฐ๋ฐ์ ๋์  ํด๊ฒฐํด์ค
>>>- ๊ฐ์ฒด๋ฅผ DB์ ์ ์ฅํ  ๋ INSERT SQL์ ์ง์  ์์ฑํ์ง ์๊ณ  ๊ฐ์ฒด๋ฅผ ์๋ฐ ์ปฌ๋ ์์ ์ ์ฅํ๋ฏ ORM ํ๋ ์์ํฌ์ ์ ์ฅํ๋ฉด๋จ
>>>- ORM ํ๋ ์์ํฌ๊ฐ ์ ์ ํ INSERT SQL์ ์์ฑํด์ DB์ ๊ฐ์ฒด๋ฅผ ์ ์ฅํด์ค
>>>```java
>>>jpa.persist(member); // ์ ์ฅ
>>>
>>>Member member = jpa.find(memberId); // ์กฐํ
>>>```
>>- ORM ํ๋ ์์ํฌ๋ ๋จ์ํ SQL์ ๊ฐ๋ฐ์ ๋์  ์์ฑํด์ DB์ ์ ๋ฌํ๋๊ฒ ๋ฟ๋ง ์๋๋ผ ๋ค์ํ ํจ๋ฌ๋ค์ ๋ถ์ผ์น ๋ฌธ์ ๋ค๋ ํด๊ฒฐํด์ค
>>- ๊ฐ์ฒด ์ธก๋ฉด์์๋ ์ ๊ตํ ๊ฐ์ฒด ๋ชจ๋ธ๋ง์ ํ  ์ ์๊ณ  ๊ด๊ณํ DB๋ DB์ ๋ง๋๋ก ๋ชจ๋ธ๋งํ๋ฉด ๋จ
>>- ๋์ ์ด๋ป๊ฒ ๋งคํํด์ผ ํ๋์ง ๋งคํ ๋ฐฉ๋ฒ๋ง ORM ํ๋ ์์ํฌ์ ์๋ ค์ฃผ๋ฉด ๋๋ฏ๋ก ๊ฐ๋ฐ์๋ DB ์ค์ฌ์ธ ๊ด๊ณํ DB๋ฅผ ์ฌ์ฉํด๋ ๊ฐ์ฒด์งํฅ ์ดํ๋ฆฌ์ผ์ด์ ๊ฐ๋ฐ์ ์ง์คํ  ์ ์์
>>- ์๋ฐ ์ง์์ ORM ํ๋ ์์ํฌ์๋ ํ์ด๋ฒ๋ค์ดํธ๊ฐ ๊ฐ์ฅ ๋ง์ด ์ฌ์ฉ๋๋ฉฐ ๊ฑฐ์ ๋๋ถ๋ถ์ ํจ๋ฌ๋ค์ ๋ถ์ผ์น ๋ฌธ์ ๋ฅผ ํด๊ฒฐํด์ฃผ๋ ์ฑ์ํ ORM ํ๋ ์์ํฌ์
>- JPA์๊ฐ
>>- ๊ณผ๊ฑฐ ์๋ฐ ์ง์์ EJB๋ผ๋ ๊ธฐ์  ํ์ค์ ๋ง๋ค์๋๋ฐ ์ํฐํฐ ๋น์ด๋ผ๋ ORM ๊ธฐ์ ๋ ํฌํจ๋์ด ์์์ผ๋ ๋ณต์กํ๊ณ  ์ฑ์๋๋ ๋จ์ด์ก์ผ๋ฉฐ J2EE ์ ํ๋ฆฌ์ผ์ด์ ์๋ฒ์์๋ง ๋์ํ์
>>- ์ด๋ EJB์ ORM ๊ธฐ์ ๊ณผ ๋น๊ตํด์ ๊ฐ๋ณ๊ณ  ์ค์ฉ์ ์ด๊ณ  ์ฑ์๋๋ ๋์ผ๋ฉฐ J2EE ์๋ฒ ์์ด๋ ๋์ํ๋ ํ์ด๋ฒ๋ค์ดํธ๋ผ๋ ์คํ์์ค ORM ํ๋ ์์ํฌ๊ฐ ๋ฑ์ฅํ์ฌ ๋ง์ ๊ฐ๋ฐ์๊ฐ ์ฌ์ฉํ์๊ณ , ๊ฒฐ๊ตญ ํ์ด๋ฒ๋ค์ดํธ๋ฅผ ๊ธฐ๋ฐ์ผ๋ก JPA๋ผ๋ ์๋ก์ด ์๋ฐ ORM ๊ธฐ์  ํ์ค์ด ๋ง๋ค์ด์ง
>>- JPA๋ ์๋ฐ ORM ๊ธฐ์ ์ ๋ํ API ํ์ค ๋ช์ธ์ด๋ฏ๋ก JPA๋ฅผ ์ฌ์ฉํ๋ ค๋ฉด JPA๋ฅผ ๊ตฌํํ ORM ํ๋ ์์ํฌ๋ฅผ ์ ํํด์ผํ๋๋ฐ ํ์ด๋ฒ๋ค์ดํธ๊ฐ ๊ฐ์ฅ ๋์ค์ ์
>>- JPA๋ผ๋ ํ์ค ๋๋ถ์ ํน์  ๊ตฌํ ๊ธฐ์ ์ ๋ํ ์์กด๋๋ฅผ ์ค์ผ ์ ์๊ณ  ๋ค๋ฅธ ๊ตฌํ ๊ธฐ์ ๋ก ์์ฝ๊ฒ ์ด๋ํ  ์ ์๋ ์ฅ์ ์ด ์์
>>- JPA ํ์ค์ ์ผ๋ฐ์ ์ด๊ณ  ๊ณตํต์ ์ธ ๊ธฐ๋ฅ์ ๋ชจ์์ด๋ฏ๋ก ํ์ค์ ๋จผ์  ์ดํดํ๊ณ  ํ์์ ๋ฐ๋ผ JPA ๊ตฌํ์ฒด๊ฐ ์ ๊ณตํ๋ ๊ณ ์ ์ ๊ธฐ๋ฅ์ ์์๊ฐ๋ฉด ๋จ
>>>- JPA 1.0 (JSP 220) 2006๋ : ์ด๊ธฐ๋ฒ์ ์ผ๋ก ๋ณตํฉํค์ ์ฐ๊ด๊ด๊ณ ๊ธฐ๋ฅ์ด ๋ถ์กฑ
>>>- JPA 2.0 (JSP 317) 2009๋ : ๋๋ถ๋ถ์ ORM ๊ธฐ๋ฅ์ ํฌํจํ๊ณ  JPA Criteria๊ฐ ์ถ๊ฐ๋จ
>>>- JPA 2.1 (JSP 338) 2013๋ : ์คํ ์ด๋ ํ๋ก์์  ์ ๊ทผ, ์ปจ๋ฒํฐ, ์ํฐํฐ ๊ทธ๋ํ ๊ธฐ๋ฅ์ด ์ถ๊ฐ๋จ
>- ์ JPA๋ฅผ ์ฌ์ฉํด์ผ ํ๋๊ฐ?
>>- ์์ฐ์ฑ
>>>- JPA๋ฅผ ์ฌ์ฉํ๋ฉด ์๋ฐ ์ปฌ๋ ์์ ๊ฐ์ฒด๋ฅผ ์ ์ฅํ๋ฏ์ด JPA์๊ฒ ์ ์ฅํ  ๊ฐ์ฒด๋ฅผ ์ ๋ฌํ๋ฉด CRUD SQL์ ์์ฑํ๊ณ  JDBC API๋ฅผ ์ฌ์ฉํ๋ ์ง๋ฃจํ๊ณ  ๋ฐ๋ณต์ ์ธ ์ผ์ JPA๊ฐ ๋์  ์ฒ๋ฆฌํด์ค
>>>- ์ถ๊ฐ์ ์ผ๋ก CREATE TABLE๊ฐ์ DDL ๋ฌธ์ ์๋์ผ๋ก ์์ฑํด์ฃผ๋ ๊ธฐ๋ฅ๋ ์์ผ๋ฏ๋ก DB ์ค๊ณ ์ค์ฌ์ ํจ๋ฌ๋ค์์ ๊ฐ์ฒด ์ค๊ณ ์ค์ฌ์ผ๋ก ์ญ์ ์ํฌ ์ ์์
>>- ์ ์ง๋ณด์
>>>- SQL์ ์ง์  ๋ค๋ฃจ๋ฉด ์ํฐํฐ์ ํ๋๋ฅผ ํ๋๋ง ์ถ๊ฐํด๋ ๊ด๋ จ๋ ๋ฑ๋ก, ์์ , ์กฐํ SQL๊ณผ ๊ฒฐ๊ณผ๋ฅผ ๋งคํํ๊ธฐ ์ํ JDBC API ์ฝ๋๋ฅผ ๋ชจ๋ ๋ณ๊ฒฝํด์ผ ํ์ผ๋ JPA๋ฅผ ์ฌ์ฉํ๋ฉด ๋์  ์ฒ๋ฆฌํด์ฃผ๋ฏ๋ก ์ ์ง๋ณด์ํด์ผ ํ๋ ์ฝ๋ ์๊ฐ ์ค์ด๋ฌ
>>- ํจ๋ฌ๋ค์์ ๋ถ์ผ์น ํด๊ฒฐ
>>>- JPA๋ ์์, ์ฐ๊ด๊ด๊ณ, ๊ฐ์ฒด ๊ทธ๋ํ ํ์, ๋น๊ตํ๊ธฐ์ ๊ฐ์ ํจ๋ฌ๋ค์์ ๋ถ์ผ์น ๋ฌธ์ ๋ฅผ ํด๊ฒฐํด์ค
>>- ์ฑ๋ฅ
>>>- JPA๋ ์ ํ๋ฆฌ์ผ์ด์๊ณผ DB ์ฌ์ด์์ ๋ค์ํ ์ฑ๋ฅ ์ต์ ํ ๊ธฐํ๋ฅผ ์ ๊ณตํจ
>>>```java
>>>String memberId = "helloId";
>>>Member member1 = jpa.find(memberId);
>>>Member member2 = jpa.find(memberId);
>>>```
>>>- JDBC API๋ฅผ ์ฌ์ฉํ๋ค๋ฉด DB์ ๋ ๋ฒ ํต์ ํด์ผํ์ง๋ง, JPA๋ฅผ ์ฌ์ฉํ๋ฉด ํ์์ ์กฐํํ๋ SQL์ ํ ๋ฒ๋ง DB์ ์ ๋ฌํ๊ณ  ๋ ๋ฒ์งธ๋ ์กฐํํ ํ์ ๊ฐ์ฒด๋ฅผ ์ฌ์ฌ์ฉํจ
>>- ๋ฐ์ดํฐ ์ ๊ทผ ์ถ์ํ์ ๋ฒค๋ ๋๋ฆฝ์ฑ
>>>- ๊ด๊ฒ DB๋ ๊ฐ์ ๊ธฐ๋ฅ๋ ๋ฒค๋๋ง๋ค ์ฌ์ฉ๋ฒ์ด ๋ค๋ฅธ ๊ฒฝ์ฐ๊ฐ ๋ง์๋ฐ ๋จ์ ์ธ ์๋ก ํ์ด์ง ์ฒ๋ฆฌ๋ DB๋ง๋ค ๋ฌ๋ผ์ ์ฌ์ฉ๋ฒ์ ๊ฐ๊ฐ ๋ฐฐ์์ผ ํ๋ฏ๋ก ์ ํ๋ฆฌ์ผ์ด์์ ์ฒ์ ์ ํํ DB ๊ธฐ์ ์ ์ข์๋๊ณ  ๋ค๋ฅธ DB๋ก ๋ณ๊ฒฝํ๊ธฐ๋ ๋งค์ฐ ์ด๋ ค์
>>>- JPA๋ ์ ํ๋ฆฌ์ผ์ด์๊ณผ DB ์ฌ์ด์ ์ถ์ํ๋ ๋ฐ์ดํฐ ์ ๊ทผ ๊ณ์ธต์ ์ ๊ณตํ์ฌ ํน์  DB ๊ธฐ์ ์ ์ข์๋์ง ์๋๋ก ํ์ฌ ๋ง์ฝ DB๋ฅผ ๋ณ๊ฒฝํ๋ฉด JPA์๊ฒ ๋ค๋ฅธ DB๋ฅผ ์ฌ์ฉํ๋ค๊ณ  ์๋ ค์ฃผ๊ธฐ๋ง ํ๋ฉด ๋จ
>>- ํ์ค
>>>- JPA๋ ์๋ฐ ์ง์์ ORM ๊ธฐ์  ํ์ค์ด๊ณ , ํ์ค์ ์ฌ์ฉํ๋ฉด ๋ค๋ฅธ ๊ตฌํ ๊ธฐ์ ๋ก ์์ฝ๊ฒ ๋ณ๊ฒฝํ  ์ ์์

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

---

## JPA ์์

>### ๋ผ์ด๋ธ๋ฌ๋ฆฌ์ ํ๋ก์ ํธ ๊ตฌ์กฐ
>- ๊ฐ์
>>- JPA ๊ตฌํ์ฒด๋ก ํ์ด๋ฒ๋ค์ดํธ๋ฅผ ์ฌ์ฉํ๊ธฐ ์ํ ํต์ฌ ๋ผ์ด๋ธ๋ฌ๋ฆฌ
>>>- hibernate-core : ํ์ด๋ฒ๋ค์ดํธ ๋ผ์ด๋ธ๋ฌ๋ฆฌ
>>>- hibernate-entitymanager : ํ์ด๋ฒ๋ค์ดํธ๊ฐ JPA ๊ตฌํ์ฒด๋ก ๋์ํ๋๋ก JPA ํ์ค์ ๊ตฌํํ ๋ผ์ด๋ธ๋ฌ๋ฆฌ
>>>- hibernate-jpa-2.1-api : JPA 2.1 ํ์ค API๋ฅผ ๋ชจ์๋ ๋ผ์ด๋ธ๋ฌ๋ฆฌ

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

>### ๊ฐ์ฒด ๋งคํ ์์
>```sql
>CREATE TABLE MEMBER (
>  ID VARCHAR(255) NOT NULL,
>  NAME VARCHAR(255),
>  AGE INTEGER NOT NULL,
>  PRIMARY KEY (ID)
>)
>```
>```java
>package jpabook.start;
>
>import javax.persistence.*;
>
>@Entity
>@Table(name="MEMBER")
>public class Member {
>
>  @Id
>  @Column(name = "ID")
>  private String id;
>
>  @Column(name = "NAME")
>  private String username;
>
>  private Integer age;
>
>  // Getter, Setter
>}
>```
>- @Entity
>>- ํด๋น ํด๋์ค๋ฅผ ํ์ด๋ธ๊ณผ ๋งคํํ๋ค๊ณ  JPA์๊ฒ ์๋ ค์ฃผ๋ ์ด๋ธํ์ด์์ผ๋ก, ํด๋น ์ด๋ธํ์ด์์ด ์ฌ์ฉ๋ ํด๋์ค๋ฅผ ์ํฐํฐ ํด๋์ค๋ผ ํจ
>- @Table
>>- ์ํฐํฐ ํด๋์ค์ ๋งคํํ  ํ์ด๋ธ ์ ๋ณด๋ฅผ ์๋ ค์ค
>>- ์ฌ๊ธฐ์๋ name ์์ฑ์ ์ฌ์ฉํ์ฌ Member ์ํฐํฐ๋ฅผ MEMBER ํ์ด๋ธ์ ๋งคํํ์
>>- ์๋ต์ ํด๋์ค ์ด๋ฆ์ ํ์ด๋ธ ์ด๋ฆ์ผ๋ก ๋งคํํจ (๋ ์ ํํ๋ ์ํฐํฐ ์ด๋ฆ์ ์ฌ์ฉํจ)
>- @Id
>>- ์ํฐํฐ ํด๋์ค์ ํ๋๋ฅผ ํ์ด๋ธ์ ๊ธฐ๋ณธ ํค์ ๋งคํํจ
>>- ํด๋น ์ด๋ธํ์ด์์ด ์ฌ์ฉ๋ ํ๋๋ฅผ ์๋ณ์ ํ๋๋ผ๊ณ  ํจ
>- @Column
>>- ํ๋๋ฅผ ์ปฌ๋ผ์ ๋งคํํจ
>>- name ์์ฑ์ ์ฌ์ฉํ์ฌ Member ์ํฐํฐ์ username ํ๋๋ฅผ MEMBER ํ์ด๋ธ์ NAME ์ปฌ๋ผ์ ๋งคํํจ
>- ๋งคํ ์ ๋ณด๊ฐ ์๋ ํ๋
>>- age ํ๋์๋ ๋งคํ ์ด๋ธํ์ด์์ด ์๋๋ฐ, ๋งคํ ์ด๋ธํ์ด์์ ์๋ตํ๋ฉด ํ๋๋ช์ ์ฌ์ฉํด์ ์ปฌ๋ผ๋ช์ผ๋ก ๋งคํํจ
>>- ํ๋๋ช์ด age์ด๋ฏ๋ก age ์ปฌ๋ผ์ผ๋ก ๋งคํํจ
>>- ๋ง์ฝ ๋์๋ฌธ์๋ฅผ ๊ตฌ๋ถํ๋ DB๋ฅผ ์ฌ์ฉํ๋ค๋ฉด @Column(name="AGE") ์ฒ๋ผ ๋ช์์ ์ผ๋ก ๋งคํํด์ผ ํจ

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

>### persistence.xml ์ค์ 
>- JPA๋ persistence.xml์ ์ฌ์ฉํ์ฌ ํ์ํ ์ค์  ์ ๋ณด๋ฅผ ๊ด๋ฆฌํจ
>- ํด๋น ์ค์  ํ์ผ์ด META-INF/persistence.xml ํด๋์ค ํจ์ค ๊ฒฝ๋ก์ ์์ผ๋ฉด ๋ณ๋์ ์ค์  ์์ด JPA๊ฐ ์ธ์ํ  ์ ์์
>>```xml
>><?xml version="1.0" encoding="UTF-8"?>
>><persistence xmlns="http://xmlns.jcp.org/xml/ns/persistence" version="2.1">
>>  <persistence-unit name="jpabook">
>>    <properties>
>>      <!-- ํ์ ์์ฑ -->
>>      <property name="javax.persistence.jdbc.driver" value="org.h2.Driver"/>
>>      <property name="javax.persistence.jdbc.user" value="sa"/>
>>      <property name="javax.persistence.jdbc.password" value=""/>
>>      <property name="javax.persistence.jdbc.url" value="jdbc:h2:tcp://localhost/~/test"/>
>>      <property name="hibernate.dialect" value="org.hibernate.dialect.H2Dialect" />
>>
>>      <!-- ์ต์ -->
>>      <property name="hibernate.show_sql" value="true" />
>>      <property name="hibernate.format_sql" value="true" />
>>      <property name="hibernate.use_sql_comments" value="true" />
>>      <property name="hibernate.id.new_generator_mappings" value="true" />
>>    </properties>
>>  </persistence-unit>
>></persistence>
>>```
>>```xml
>><persistence xmlns="http://xmlns.jcp.org/xml/ns/persistence" version="2.1">
>>```
>>- ์ค์  ํ์ผ์ persistence๋ก ์์ํ๋ฉฐ XML ๋ค์์คํ์ด์ค์ ์ฌ์ฉํ  ๋ฒ์ ์ ์ง์ ํจ
>>```xml
>><persistence-unit name="jpabook">
>>```
>>- JPA ์ค์ ์ ์์์ฑ ์ ๋๋ถํฐ ์์ํ๋๋ฐ ์ผ๋ฐ์ ์ผ๋ก ์ฐ๊ฒฐํ  DB ํ๋๋น ์์์ฑ ์ ๋์ ๋ฑ๋กํ๋ฉฐ ์์์ฑ ์ ๋์๋ ๊ณ ์ ํ ์ด๋ฆ์ ๋ถ์ฌํด์ผ ํจ
>>```xml
>><properties>
>>  <!-- ํ์ ์์ฑ -->
>>  <property name="javax.persistence.jdbc.driver" value="org.h2.Driver"/>
>>  <property name="javax.persistence.jdbc.user" value="sa"/>
>>  <property name="javax.persistence.jdbc.password" value=""/>
>>  <property name="javax.persistence.jdbc.url" value="jdbc:h2:tcp://localhost/~/test"/>
>>  <property name="hibernate.dialect" value="org.hibernate.dialect.H2Dialect" />
>>  ...
>>```
>>- JPA ํ์ค ์์ฑ
>>>- javax.persistence.jdbc.driver : JDBC ๋๋ผ์ด๋ฒ
>>>- javax.persistence.jdbc.user : DB ์ ์ ์์ด๋
>>>- javax.persistence.jdbc.password : DB ์ ์ ๋น๋ฐ๋ฒํธ
>>>- javax.persistence.jdbc.url : DB ์ ์ URL
>>- ํ์ด๋ฒ๋ค์ดํธ ์์ฑ
>>>- hibernate.dialect : ๋ฐ์ดํฐ๋ฒ ์ด์ค ๋ฐฉ์ธ(Dialect) ์ค์ 
>>- ์ด๋ฆ์ด javax.persistence๋ก ์์ํ๋ ์์ฑ์ JPA ํ์ค ์์ฑ์ผ๋ก ํน์  ๊ตฌํ์ฒด์ ์ข์๋์ง ์์
>>- ๋ฐ๋ฉด์ hibernate๋ก ์์ํ๋ ์์ฑ์ ํ์ด๋ฒ๋ค์ดํธ ์ ์ฉ ์์ฑ์
>- ๋ฐ์ดํฐ๋ฒ ์ด์ค ๋ฐฉ์ธ
>>- JPA๋ ํน์  DB์ ์ข์์ ์ด์ง ์์ ๊ธฐ์ ์ด๋ฏ๋ก ๋ค๋ฅธ DB๋ก ์์ฝ๊ฒ ๊ต์ฒดํ  ์ ์์ผ๋, ๊ฐ DB๋ง๋ค ์ ๊ณตํ๋ SQL ๋ฌธ๋ฒ๊ณผ ํจ์๊ฐ ์กฐ๊ธ์ฉ ๋ค๋ฅธ ๋ฌธ์ ์ ์ด ์์
>>- DB๋ณ ์ฐจ์ด์  ์์
>>>- ๋ฐ์ดํฐ ํ์ : ๊ฐ๋ณ ๋ฌธ์ ํ์์ผ๋ก MySQl์ VARCHAR, ์ค๋ผํด์ VARCHAR2๋ฅผ ์ฌ์ฉํจ
>>>- ๋ค๋ฅธ ํจ์๋ช : ๋ฌธ์์ด์ ์๋ฅด๋ ํจ์๋ก SQL ํ์ค์ SUBSTRING(), ์ค๋ผํด์ SUBSTR()์ ์ฌ์ฉํจ
>>>- ํ์ด์ง ์ฒ๋ฆฌ : MySQL์ LIMIT, ์ค๋ผํด์ ROWNUM์ ์ฌ์ฉํจ
>>- ์ด์ฒ๋ผ SQL ํ์ค์ ์งํค์ง ์๊ฑฐ๋ ํน์  DB๋ง์ ๊ณ ์ ํ ๊ธฐ๋ฅ์ JPA์์๋ ๋ฐฉ์ธ(Dialect)๋ผ ํจ
>>- ์ ํ๋ฆฌ์ผ์ด์ ๊ฐ๋ฐ์๊ฐ ํน์  ๋ฐ์ดํฐ๋ฒ ์ด์ค์ ์ข์๋๋ ๊ธฐ๋ฅ์ ๋ง์ด ์ฌ์ฉํ๋ฉด ์ถํ DB ๊ต์ฒด๊ฐ ์ด๋ ค์ธ ์ ์์
>>- ํ์ด๋ฒ๋ค์ดํธ๋ฅผ ํฌํจํ ๋๋ถ๋ถ์ JPA ๊ตฌํ์ฒด๋ค์ ์ด๋ฐ ๋ฌธ์ ๋ฅผ ํด๊ฒฐํ๊ณ ์ ๋ค์ํ DB ๋ฐฉ์ธ ํด๋์ค๋ฅผ ์ ๊ณตํจ
>```xml
><!-- ์ต์ -->
><property name="hibernate.show_sql" value="true" />
><property name="hibernate.format_sql" value="true" />
><property name="hibernate.use_sql_comments" value="true" />
><property name="hibernate.id.new_generator_mappings" value="true" />
>```
>- hibernate.show_sql : ํ์ด๋ฒ๋ค์ดํธ๊ฐ ์คํํ SQL์ ์ถ๋ ฅํจ
>- hibernate.format_sql : ํ์ด๋ฒ๋ค์ดํธ๊ฐ ์คํํ SQL์ ์ถ๋ ฅํ  ๋ ๋ณด๊ธฐ ์ฝ๊ฒ ์ ๋ ฌํจ
>- hibernate.use_sql_comments : ์ฟผ๋ฆฌ๋ฅผ ์ถ๋ ฅํ  ๋ ์ฃผ์๋ ํจ๊ป ์ถ๋ ฅํจ
>- hibernate.id.new_generator_mappings : JPA ํ์ค์ ๋ง์ถ ์๋ก์ด ํค ์์ฑ ์ ๋ต์ ์ฌ์ฉํจ

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

>### ์ ํ๋ฆฌ์ผ์ด์ ๊ฐ๋ฐ
>```java
>package jpabook.start;
>
>import javax.persistence.*;
>import java.util.List;
>
>public class JpaMain {
>  public static void main(String[] args) {
>
>    // ์ํฐํฐ ๋งค๋์  ํฉํ ๋ฆฌ ์์ฑ
>    EntityManagerFactory emf = Persistence.createEntityManagerFactory("jpabook");
>    EntityManager em = emf.createEntityManager(); // ์ํฐํฐ ๋งค๋์  ์์ฑ
>
>    EntityTransaction tx = em.getTransaction(); // ํธ๋์ญ์ ๊ธฐ๋ฅ ํ๋
>
>    try {
>        tx.begin(); // ํธ๋์ญ์ ์์
>        logic(em);  // ๋น์ฆ๋์ค ๋ก์ง
>        tx.commit();// ํธ๋์ญ์ ์ปค๋ฐ
>    } catch (Exception e) {
>        e.printStackTrace();
>        tx.rollback(); // ํธ๋์ญ์ ๋กค๋ฐฑ
>    } finally {
>        em.close(); // ์ํฐํฐ ๋งค๋์  ์ข๋ฃ
>    }
>
>    emf.close(); // ์ํฐํฐ ๋งค๋์  ํฉํ ๋ฆฌ ์ข๋ฃ
>  }
>
>  public static void logic(EntityManager em) {
>    String id = "id1";
>    Member member = new Member();
>    member.setId(id);
>    member.setUsername("์งํ");
>    member.setAge(2);
>
>    // ๋ฑ๋ก
>    em.persist(member);
>
>    // ์์ 
>    member.setAge(20);
>
>    // ํ ๊ฑด ์กฐํ
>    Member findMember = em.find(Member.class, id);
>    System.out.println("findMember=" + findMember.getUsername() + ", age=" + findMember.getAge());
>
>    // ๋ชฉ๋ก ์กฐํ
>    List<Member> members = em.createQuery("select m from Member m", Member.class).getResultList();
>    System.out.println("members.size=" + members.size());
>
>    // ์ญ์ 
>    em.remove(member);
>  }
>}
>```
>- ํฌ๊ฒ 3๋ถ๋ถ์ผ๋ก ๋๋  ์ค๋ช
>>- ์ํฐํฐ ๋งค๋์  ์ค์ 
>>- ํธ๋์ญ์ ๊ด๋ฆฌ
>>- ๋น์ฆ๋์ค ๋ก์ง
>- ์ํฐํฐ ๋งค๋์  ์ค์ 
>>- ์ํฐํฐ ๋งค๋์  ํฉํ ๋ฆฌ ์์ฑ
>>>- JPA๋ฅผ ์์ํ๋ ค๋ฉด ์ฐ์  persistence.xml ์ ์ค์  ์ ๋ณด๋ฅผ ์ฌ์ฉํ์ฌ ์ํฐํฐ ๋งค๋์  ํฉํ ๋ฆฌ๋ฅผ ์์ฑํจ
>>>- Persistence ํด๋์ค๋ ์ํฐํฐ ๋งค๋์  ํฉํ ๋ฆฌ๋ฅผ ์์ฑํ์ฌ JPA๋ฅผ ์ฌ์ฉํ  ์ ์๊ฒ ์ค๋นํจ
>>>>```java
>>>>EntityManagerFactory emf = Persistence.createEntityManagerFactory("jpabook");
>>>>```
>>>- ํด๋น ์ฝ๋๋ฅผ ์คํ ์ META-INF/persistence.xml ์์ ์ด๋ฆ์ด jpabook์ธ ์์์ฑ ์ ๋์ ์ฐพ์ ์ํฐํฐ ๋งค๋์  ํฉํ ๋ฆฌ๋ฅผ ์์ฑํจ
>>>- ์ด๋ persistence.xml ์ ์ค์  ์ ๋ณด๋ฅผ ์ฝ์ด JPA๋ฅผ ๋์์ํค๊ธฐ ์ํ ๊ธฐ๋ฐ ๊ฐ์ฒด๋ฅผ ๋ง๋ค๊ณ  JPA ๊ตฌํ์ฒด์ ๋ฐ๋ผ์๋ DB ์ปค๋ฅ์ ํ๋ ์์ฑํ๋ฏ๋ก ์ํฐํฐ ๋งค๋์  ํฉํ ๋ฆฌ์ ์์ฑ ๋น์ฉ์ ์์ฃผ ํฌ๋ฏ๋ก ์ ํ๋ฆฌ์ผ์ด์ ์ ์ฒด์์ ๋ฑ ํ ๋ฒ๋ง ์์ฑํ๊ณ  ๊ณต์ ํ์ฌ ์ฌ์ฉํ๋๊ฒ์ ๊ถ์ฅํจ
>>- ์ํฐํฐ ๋งค๋์  ์์ฑ 
>>>```java
>>>EntityManager em = emf.createEntityManager();
>>>```
>>>- ์ํฐํฐ ๋งค๋์  ํฉํ ๋ฆฌ์์ ์ํฐํฐ ๋งค๋์ ๋ฅผ ์์ฑํจ
>>>- JPA์ ๊ธฐ๋ฅ ๋๋ถ๋ถ์ ์ํฐํฐ ๋งค๋์ ๊ฐ ์ ๊ณตํจ
>>>>- ๋ํ์ ์ผ๋ก ์ํฐํฐ ๋งค๋์ ๋ฅผ ์ฌ์ฉํด์ ์ํฐํฐ๋ฅผ DB์ CRUDํ  ์ ์์
>>>- ์ํฐํฐ ๋งค๋์ ๋ ๋ด๋ถ์ ๋ฐ์ดํฐ์์ค(DB ์ปค๋ฅ์)๋ฅผ ์ ์งํ๋ฉด์ DB์ ํต์ ํ๋ฏ๋ก ์ ํ๋ฆฌ์ผ์ด์ ๊ฐ๋ฐ์๋ ์ํฐํฐ ๋งค๋์ ๋ฅผ ๊ฐ์์ DB๋ก ์๊ฐํ  ์ ์์
>>>- ์ฐธ๊ณ ๋ก ์ํฐํฐ ๋งค๋์ ๋ DB ์ปค๋ฅ์๊ณผ ๋ฐ์ ํ ๊ด๊ณ๊ฐ ์์ผ๋ฏ๋ก ์ค๋ ๋๊ฐ์ ๊ณต์ ํ๊ฑฐ๋ ์ฌ์ฌ์ฉํ๋ฉด ์๋จ
>>- ์ข๋ฃ
>>>```java
>>>em.close();
>>>emf.close();
>>>```
>>>- ์ฌ์ฉ์ด ๋๋ ์ํฐํฐ ๋งค๋์ ๋ ๋ค์์ฒ๋ผ ๋ฐ๋์ ์ข๋ฃํด์ผํ๋ฉฐ, ์ ํ๋ฆฌ์ผ์ด์์ ์ข๋ฃํ  ๋ ์ํฐํฐ ๋งค๋์  ํฉํ ๋ฆฌ๋ ์ข๋ฃํด์ผ ํจ
>- ํธ๋์ญ์ ๊ด๋ฆฌ
>>```java
>>EntityTransaction tx = em.getTransaction();
>>
>>try {
>>    tx.begin();
>>    logic(em);
>>    tx.commit();
>>} catch (Exception e) {
>>    tx.rollback();
>>}
>>```
>>- JPA์์ ํธ๋์ญ์ ์์ด ๋ฐ์ดํฐ๋ฅผ ๋ณ๊ฒฝํ๋ฉด ์์ธ๊ฐ ๋ฐ์ํ๋ฏ๋ก JPA๋ฅผ ์ฌ์ฉํ๋ฉด ํญ์ ํธ๋์ญ์ ์์์ ๋ฐ์ดํฐ๋ฅผ ๋ณ๊ฒฝํด์ผํจ
>>- ํธ๋์ญ์์ ์์ํ๋ ค๋ฉด ์ํฐํฐ ๋งค๋์ ์์ ํธ๋์ญ์ API๋ฅผ ๋ฐ์์์ผํจ
>>- ํธ๋์ญ์ API๋ฅผ ์ฌ์ฉํ์ฌ ๋น์ฆ๋์ค ๋ก์ง์ด ์ ์ ๋์ํ๋ฉด ํธ๋์ญ์์ ์ปค๋ฐํ๊ณ  ์์ธ๊ฐ ๋ฐ์ํ๋ฉด ํธ๋์ญ์์ ๋กค๋ฐฑํจ
>- ๋น์ฆ๋์ค ๋ก์ง
>>```java
>>public static void logic(EntityManager em) {
>>  String id = "id1";
>>  Member member = new Member();
>>  member.setId(id);
>>  member.setUsername("์งํ");
>>  member.setAge(2);
>>
>>  em.persist(member);
>>
>>  member.setAge(20);
>>
>>  Member findMember = em.find(Member.class, id);
>>  System.out.println("findMember=" + findMember.getUsername() + ", age=" + findMember.getAge());
>>
>>  List<Member> members = em.createQuery("select m from Member m", Member.class).getResultList();
>>  System.out.println("members.size=" + members.size());
>>
>>  em.remove(member);
>>}
>>```
>>- ์ถ๋ ฅ ๊ฒฐ๊ณผ
>>>```
>>>findMember=์งํ, age=20
>>>members.size=1
>>>```
>>- ๋น์ฆ๋์ค ๋ก์ง์ ๋ณด๋ฉด CRUD ์์์ด ์ํฐํฐ ๋งค๋์ ๋ฅผ ํตํด์ ์ํ๋๋ ๊ฒ์ ์ ์ ์์
>>- ์ํฐํฐ ๋งค๋์ ๋ ๊ฐ์ฒด๋ฅผ ์ ์ฅํ๋ ๊ฐ์์ DB์ฒ๋ผ ๋ณด์
>>- ๋ฑ๋ก
>>>- ์ํฐํฐ๋ฅผ ์ ์ฅํ๋ ค๋ฉด ์ํฐํฐ ๋งค๋์ ์ persist() ๋ฉ์๋์ ์ ์ฅํ  ์ํฐํฐ๋ฅผ ๋๊ฒจ์ฃผ๋ฉด ๋จ
>>>- JPA๋ ํ์ ์ํฐํฐ์ ๋งคํ ์ ๋ณด(์ด๋ธํ์ด์)์ ๋ถ์ํด์ ๋ค์๊ณผ ๊ฐ์ SQL์ ๋ง๋ค์ด DB์ ์ ๋ฌํจ
>>>>```sql
>>>>INSERT INTO MEMBER (ID, NAME, AGE) VALUES ('id1', '์งํ', 2)
>>>>```
>>- ์์ 
>>>- ์ํฐํฐ๋ฅผ ์์ ํ ํ ์์  ๋ด์ฉ์ ๋ฐ์ํ๋ ค๋ฉด em.update() ๊ฐ์ ๋ฉ์๋๋ฅผ ํธ์ถํด์ผ ํ  ๊ฒ ๊ฐ์๋ฐ ๋จ์ํ ์ํฐํฐ์ ๊ฐ๋ง ๋ณ๊ฒฝํ์์
>>>- JPA๋ ์ด๋ค ์ํฐํฐ๊ฐ ๋ณ๊ฒฝ๋์๋์ง ์ถ์ ํ๋ ๊ธฐ๋ฅ์ ๊ฐ์ถ๊ณ  ์์ด์ ์ํฐํฐ์ ๊ฐ๋ง ๋ณ๊ฒฝํ๋ฉด ๋ค์๊ณผ ๊ฐ์ UPDATE SQL์ ์์ฑํ์ฌ DB์ ๊ฐ์ ๋ณ๊ฒฝํจ
>>>>```sql
>>>>UPDATE MEMBER
>>>>  SET AGE=20, NAME='์งํ'
>>>>WHERE ID='id1'
>>>>```
>>- ์์ 
>>>- ์ํฐํฐ๋ฅผ ์ญ์ ํ๋ ค๋ฉด ์ํฐํฐ ๋งค๋์ ์ remove() ๋ฉ์๋์ ์ญ์ ํ๋ ค๋ ์ํฐํฐ๋ฅผ ๋๊ฒจ์ค
>>>- JPA๋ ๋ค์ DELETE SQL์ ์์ฑํ์ฌ ์คํํจ
>>>>```sql
>>>>DELETE FROM MEMBER WHERE ID='id1'
>>>>```
>>- ํ ๊ฑด ์กฐํ
>>>- find() ๋ฉ์๋๋ ์กฐํํ  ์ํฐํฐ ํ์๊ณผ @Id๋ก DB ํ์ด๋ธ์ ๊ธฐ๋ณธ ํค์ ๋งคํํ ์๋ณ์ ๊ฐ์ผ๋ก ์ํฐํฐ ํ๋๋ฅผ ์กฐํํ๋ ๊ฐ์ฅ ๋จ์ํ ์กฐํ ๋ฉ์๋์
>>>- ํด๋น ๋ฉ์๋๋ฅผ ํธ์ถํ๋ฉด ๋ค์ SELECT SQL์ ์์ฑํ์ฌ DB์ ์กฐํํ ๊ฒฐ๊ณผ ๊ฐ์ผ๋ก ์ํฐํฐ๋ฅผ ์์ฑํ์ฌ ๋ฐํํจ
>>>>```sql
>>>>SELECT * FROM MEMBER WHERE ID='id1'
>>>>```
>- JPQL
>>- JPA๋ฅผ ์ฌ์ฉํ๋ฉด ์ ํ๋ฆฌ์ผ์ด์ ๊ฐ๋ฐ์๋ ์ํฐํฐ ๊ฐ์ฒด๋ฅผ ์ค์ฌ์ผ๋ก ๊ฐ๋ฐํ๊ณ  DB์ ๋ํ ์ฒ๋ฆฌ๋ JPA์ ๋งก๊ฒจ์ผ ํจ
>>- JPA๋ ์ํฐํฐ ๊ฐ์ฒด๋ฅผ ์ค์ฌ์ผ๋ก ๊ฐ๋ฐํ๋ฏ๋ก ๊ฒ์์ ํ  ๋๋ ํ์ด๋ธ์ด ์๋ ์ํฐํฐ ๊ฐ์ฒด๋ฅผ ๋์์ผ๋ก ๊ฒ์ํด์ผ ํจ
>>- ํ์ด๋ธ์ด ์๋ ์ํฐํฐ ๊ฐ์ฒด๋ฅผ ๋์์ผ๋ก ๊ฒ์ํ๋ ค๋ฉด DB์ ๋ชจ๋  ๋ฐ์ดํฐ๋ฅผ ์ ํ๋ฆฌ์ผ์ด์์ผ๋ก ๋ถ๋ฌ์์ ์ํฐํฐ ๊ฐ์ฒด๋ก ๋ณ๊ฒฝํ ๋ค์ ๊ฒ์ํด์ผํ๋๋ฐ ์ฌ์ค์ ๋ถ๊ฐ๋ฅํจ
>>- ์ ํ๋ฆฌ์ผ์ด์์ด ํ์ํ ๋ฐ์ดํฐ๋ง DB์์ ๋ถ๋ฌ์ค๋ ค๋ฉด ๊ฒฐ๊ตญ ๊ฒ์ ์กฐ๊ฑด์ด ํฌํจ๋ SQL์ ์ฌ์ฉํด์ผ ํจ
>>- JPA๋ JPQL (Java Persistence Query Language) ์ด๋ผ๋ ์ฟผ๋ฆฌ ์ธ์ด๋ก ๋ฌธ์ ๋ฅผ ํด๊ฒฐํจ
>>- JPQL์ SQL์ ์ถ์ํํ ๊ฐ์ฒด์งํฅ ์ฟผ๋ฆฌ ์ธ์ด์
>>- JPQL์ SQL ๋ฌธ๋ฒ๊ณผ ๊ฑฐ์ ์ ์ฌํ์ฌ SELECT, FROM, WHERE, GROUP BY, HAVING, JOIN ๋ฑ์ ์ฌ์ฉํ  ์ ์์
>- JPQL๊ณผ SQL์ ์ฐจ์ด์ 
>>- JPQL์ ์ํฐํฐ ๊ฐ์ฒด๋ฅผ ๋์์ผ๋ก ์ฟผ๋ฆฌํจ ์ฆ, ํด๋์ค์ ํ๋๋ฅผ ๋์์ผ๋ก ์ฟผ๋ฆฌํจ
>>- SQL์ DB ํ์ด๋ธ์ ๋์์ผ๋ก ์ฟผ๋ฆฌํจ
>- ํ๋ ์ด์์ ํ์ ๋ชฉ๋ก์ ์กฐํํ๋ ์ฝ๋
>>```java
>>TypedQuery<Member> query = em.createQuery("select m from Member m", Member.class);
>>List<Member> members = query.getresultList();
>>```
>>- select m from Member m ์ด JPQL์ด๊ณ , ์ฌ๊ธฐ์ from Member ๋ ํ์ ์ํฐํฐ ๊ฐ์ฒด๋ฅผ ๋งํ๋ ๊ฒ์ด์ง MEMBER ํ์ด๋ธ์ด ์๋
>>- JPQL์ DB ํ์ด๋ธ์ ์ ํ ์์ง ๋ชปํจ
>>- JPQL์ ์ฌ์ฉํ๋ ค๋ฉด ๋จผ์  em.createQuery(JPQL, ๋ฐํ ํ์) ๋ฉ์๋๋ฅผ ์คํํ์ฌ ์ฟผ๋ฆฌ ๊ฐ์ฒด๋ฅผ ์์ฑํ ํ ์ฟผ๋ฆฌ ๊ฐ์ฒด์ getResultList() ๋ฉ์๋๋ฅผ ํธ์ถํจ
>>- JPA๋ JPQL์ ๋ถ์ํ์ฌ ์ ์ ํ SQL์ ๋ง๋ค์ด DB์์ ๋ฐ์ดํฐ๋ฅผ ์กฐํํจ
>>>```sql
>>>SELECT M.ID, M.NAME, M.AGE FROM MEMBER M
>>>```

<br>

[๋ชฉ์ฐจ๋ก ์ด๋](#๋ชฉ์ฐจ)

---

## ์์์ฑ ๊ด๋ฆฌ

>### ์ํฐํฐ ๋งค๋์  ํฉํ ๋ฆฌ์ ์ํฐํฐ ๋งค๋์ 
>- ๊ฐ์
>>- 