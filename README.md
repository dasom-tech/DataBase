# 🤓 SQL 레벨업!!  
### 🔔 SELECT 쿼리문 실행시 순서   
      FROM -> WHERE -> GROUP BY -> HAVING -> SELECT -> ORDER BY  
      
### 🔔 NVL 함수는 값이 null인 경우 지정값을 출력, NVL2 함수는 null이 아닌경우 지정값1을 출력하고, null인 경우 지정값2를 출력 한다.    
      NVL(NAME, 'NO name')
      NVL2(NAME, NAME, 'NO name')

<details>
  <summary>SELECT</summary>  
  
  📄 테이블  
  ![image](https://user-images.githubusercontent.com/73812196/124098265-5c656d80-da97-11eb-9ff1-465d9cb857f3.png)
  
- 동물 보호소에 들어온 모든 동물의 정보를 ANIMAL_ID순으로 조회하는 SQL문을 작성해주세요. SQL을 실행하면 다음과 같이 출력되어야 합니다.  
  
  SELECT *  
  FROM ANIMAL_INS  
  ORDER BY ANIMAL_ID ASC;    
  
  📄 결과
  ![image](https://user-images.githubusercontent.com/73812196/124098315-68512f80-da97-11eb-8b3a-0eb25b5103a2.png)  
  
- 동물 보호소에 들어온 모든 동물의 이름과 보호 시작일을 조회하는 SQL문을 작성해주세요. 이때 결과는 ANIMAL_ID 역순으로 보여주세요. SQL을 실행하면 다음과 같이 출력되어야 합니다.  
  
  SELECT NAME  
     , DATETIME  
  FROM ANIMAL_INS  
  ORDER BY ANIMAL_ID DESC;    
  
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124099277-515f0d00-da98-11eb-9e1e-97c0bf135f63.png)  
  
- 동물 보호소에 들어온 동물 중 아픈 동물1의 아이디와 이름을 조회하는 SQL 문을 작성해주세요. 이때 결과는 아이디 순으로 조회해주세요.  
  
  SELECT ANIMAL_ID  
     , NAME  
  FROM ANIMAL_INS  
  WHERE INTAKE_CONDITION = 'Sick'  
  ORDER BY ANIMAL_ID ASC;    
  
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124099517-92572180-da98-11eb-98ef-2db44c947856.png)  
  
- 동물 보호소에 들어온 동물 중 젊은 동물1의 아이디와 이름을 조회하는 SQL 문을 작성해주세요. 이때 결과는 아이디 순으로 조회해주세요.  
  
  SELECT ANIMAL_ID  
       , NAME  
  FROM ANIMAL_INS  
  WHERE INTAKE_CONDITION NOT IN 'Aged'  
  ORDER BY ANIMAL_ID ASC;    
  
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124099654-b9155800-da98-11eb-97a6-3c220c2b227e.png)  
  
- 동물 보호소에 들어온 모든 동물의 아이디와 이름, 보호 시작일을 이름 순으로 조회하는 SQL문을 작성해주세요. 단, 이름이 같은 동물 중에서는 보호를 나중에 시작한 동물을 먼저 보여줘야 합니다.  
  
  SELECT ANIMAL_ID  
     , NAME  
     , DATETIME  
  FROM ANIMAL_INS  
  ORDER BY NAME ASC, DATETIME DESC;    
  
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124099909-ecf07d80-da98-11eb-8d4f-18f70489fc13.png)  
  
- 동물 보호소에 가장 먼저 들어온 동물의 이름을 조회하는 SQL 문을 작성해주세요.  
  
  SELECT NAME  
  FROM ANIMAL_INS  
  WHERE DATETIME = (SELECT MIN(DATETIME)  
                    FROM ANIMAL_INS);    
  
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124100042-13161d80-da99-11eb-915e-c0e0a0c2cbd7.png)  
</details>  
<details>
  <summary>SUM, MAX, MIN</summary>  
  
  📄 테이블    
  ![image](https://user-images.githubusercontent.com/73812196/124098265-5c656d80-da97-11eb-9ff1-465d9cb857f3.png)  
  
- 가장 최근에 들어온 동물은 언제 들어왔는지 조회하는 SQL 문을 작성해주세요.  
  
  SELECT MAX(DATETIME)  
  FROM ANIMAL_INS;  
  
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124201699-a0965380-db13-11eb-8269-f05c6365beda.png)  
  
- 동물 보호소에 가장 먼저 들어온 동물은 언제 들어왔는지 조회하는 SQL 문을 작성해주세요.  
  
  SELECT MIN(DATETIME)  
  FROM ANIMAL_INS;  
  
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124201762-c6235d00-db13-11eb-9456-23eec846f1c5.png)  
  
- 동물 보호소에 동물이 몇 마리 들어왔는지 조회하는 SQL 문을 작성해주세요.  
  
  SELECT COUNT(ANIMAL_ID)  
  FROM ANIMAL_INS;  
  
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124201803-e8b57600-db13-11eb-80c0-3cfe9c8defd6.png)  
  
- 동물 보호소에 들어온 동물의 이름은 몇 개인지 조회하는 SQL 문을 작성해주세요. 이때 이름이 NULL인 경우는 집계하지 않으며 중복되는 이름은 하나로 칩니다.
  
  SELECT COUNT(DISTINCT(NAME))  
  FROM ANIMAL_INS  
  WHERE NAME NOT IN('NULL'); 
  
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124201858-169aba80-db14-11eb-8f47-40a95c6dda4f.png)  
</details>  
<details>
  <summary>GROUP BY, HAVING</summary>  
  
  📄 테이블  
  ![image](https://user-images.githubusercontent.com/73812196/124098265-5c656d80-da97-11eb-9ff1-465d9cb857f3.png)  
  
- 동물 보호소에 들어온 동물 중 고양이와 개가 각각 몇 마리인지 조회하는 SQL문을 작성해주세요. 이때 고양이를 개보다 먼저 조회해주세요.  
  
  SELECT ANIMAL_TYPE  
     , COUNT(ANIMAL_ID) AS count  
  FROM ANIMAL_INS  
  GROUP BY ANIMAL_TYPE  
  ORDER BY ANIMAL_TYPE ASC;  
  
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124202093-9b85d400-db14-11eb-9391-bbf67116756c.png)  
  
- 동물 보호소에 들어온 동물 이름 중 두 번 이상 쓰인 이름과 해당 이름이 쓰인 횟수를 조회하는 SQL문을 작성해주세요. 이때 결과는 이름이 없는 동물은 집계에서 제외하며, 결과는 이름 순으로 조회해주세요.  
  
  SELECT NAME  
     , COUNT(NAME) AS count  
  FROM ANIMAL_INS  
  GROUP BY NAME HAVING COUNT(NAME) >= 2  
  ORDER BY NAME ASC; 
  
  📄 결과    
  ![image](https://user-images.githubusercontent.com/73812196/124202169-ccfe9f80-db14-11eb-804b-8a54b23d98e8.png)  
  
  📄 테이블  
  ![image](https://user-images.githubusercontent.com/73812196/124202316-0afbc380-db15-11eb-873b-bdbd14ca7e30.png)  
  
- 보호소에서는 몇 시에 입양이 가장 활발하게 일어나는지 알아보려 합니다. 09:00부터 19:59까지, 각 시간대별로 입양이 몇 건이나 발생했는지 조회하는 SQL문을 작성해주세요. 이때 결과는 시간대 순으로 정렬해야 합니다.  
  
  SELECT EXTRACT(HOUR FROM CAST(DATETIME AS TIMESTAMP)) AS HOUR  
     , COUNT(ANIMAL_ID) AS COUNT  
  FROM ANIMAL_OUTS A  
  WHERE EXTRACT(HOUR FROM CAST(DATETIME AS TIMESTAMP)) BETWEEN 9 AND 19  
  GROUP BY EXTRACT(HOUR FROM CAST(DATETIME AS TIMESTAMP))  
  ORDER BY HOUR;  
  
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124202400-39799e80-db15-11eb-8ac3-99b6adf990e2.png)  
  
- 보호소에서는 몇 시에 입양이 가장 활발하게 일어나는지 알아보려 합니다. 0시부터 23시까지, 각 시간대별로 입양이 몇 건이나 발생했는지 조회하는 SQL문을 작성해주세요. 이때 결과는 시간대 순으로 정렬해야 합니다.  
  
  SELECT HOUR, COUNT(B.DATETIME) AS COUNT  
  FROM  
     (SELECT LEVEL-1 AS HOUR --LEVEL은 기본으로 1부터 시작  
      FROM DUAL    
      CONNECT BY LEVEL<25) A   
  LEFT JOIN ANIMAL_OUTS B --데이터가 없어도 출력되어야 하므로 LEFT JOIN  
  ON A.HOUR = TO_CHAR(B.DATETIME,'HH24')  
  GROUP BY HOUR   
  ORDER BY HOUR;  
                           
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124205529-61203500-db1c-11eb-8c32-b00efec820bf.png)   
</details>
<details>
  <summary>IS NULL</summary>  
  
  📄 테이블  
  ![image](https://user-images.githubusercontent.com/73812196/124098265-5c656d80-da97-11eb-9ff1-465d9cb857f3.png)  
  
- 동물 보호소에 들어온 동물 중, 이름이 없는 채로 들어온 동물의 ID를 조회하는 SQL 문을 작성해주세요. 단, ID는 오름차순 정렬되어야 합니다.  
  
  SELECT ANIMAL_ID
  FROM ANIMAL_INS
  WHERE NAME IS NULL
  ORDER BY ANIMAL_ID;  
  
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124206008-6a5dd180-db1d-11eb-9d57-bd5054d82f91.png)  
  
- 동물 보호소에 들어온 동물 중, 이름이 있는 동물의 ID를 조회하는 SQL 문을 작성해주세요. 단, ID는 오름차순 정렬되어야 합니다.  
  
  SELECT ANIMAL_ID  
  FROM ANIMAL_INS  
  WHERE NAME IS NOT NULL  
  ORDER BY ANIMAL_ID;  
  
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124206192-d3dde000-db1d-11eb-84c1-238d06cab297.png)  
  
- 입양 게시판에 동물 정보를 게시하려 합니다. 동물의 생물 종, 이름, 성별 및 중성화 여부를 아이디 순으로 조회하는 SQL문을 작성해주세요. 이때 프로그래밍을 모르는 사람들은 NULL이라는 기호를 모르기 때문에, 이름이 없는 동물의 이름은 "No name"으로 표시해 주세요.  
  
  SELECT ANIMAL_TYPE  
       , NVL(NAME, 'No name')  
       , SEX_UPON_INTAKE  
  FROM ANIMAL_INS  
  ORDER BY ANIMAL_ID;  
  
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124207379-57003580-db20-11eb-99a9-14989eb3bfc7.png)  
  ![image](https://user-images.githubusercontent.com/73812196/124207410-6b443280-db20-11eb-9273-172e2053b80a.png)  
</details> 

<details>
  <summary>JOIN</summary>
  
  📄 테이블  
  ![image](https://user-images.githubusercontent.com/73812196/124098265-5c656d80-da97-11eb-9ff1-465d9cb857f3.png)  
  ![image](https://user-images.githubusercontent.com/73812196/124202316-0afbc380-db15-11eb-873b-bdbd14ca7e30.png)  
  
- ANIMAL_OUTS 테이블은 동물 보호소에서 입양 보낸 동물의 정보를 담은 테이블입니다. ANIMAL_OUTS 테이블의 ANIMAL_ID는 ANIMAL_INS의 ANIMAL_ID의 외래 키입니다. 천재지변으로 인해 일부 데이터가 유실되었습니다. 입양을 간 기록은 있는데, 보호소에 들어온 기록이 없는 동물의 ID와 이름을 ID 순으로 조회하는 SQL문을 작성해주세요.  
  
  SELECT A.ANIMAL_ID  
       , A.NAME  
  FROM ANIMAL_OUTS A  
  LEFT JOIN ANIMAL_INS B  
  ON A.ANIMAL_ID = B.ANIMAL_ID  
  WHERE B.ANIMAL_ID IS NULL  
  ORDER BY A.ANIMAL_ID;   
  
  📄 결과   
  ![image](https://user-images.githubusercontent.com/73812196/124208601-d3941380-db22-11eb-98fa-86fe80c7ca4d.png)  
  
- 관리자의 실수로 일부 동물의 입양일이 잘못 입력되었습니다. 보호 시작일보다 입양일이 더 빠른 동물의 아이디와 이름을 조회하는 SQL문을 작성해주세요. 이때 결과는 보호 시작일이 빠른 순으로 조회해야합니다.  
  
  SELECT A.ANIMAL_ID  
       , A.NAME  
  FROM ANIMAL_INS A  
  FULL OUTER JOIN ANIMAL_OUTS B  
  ON A.ANIMAL_ID = B.ANIMAL_ID  
  WHERE A.DATETIME > B.DATETIME  
  ORDER BY A.DATETIME;  
  
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124208980-b449b600-db23-11eb-9d8e-765e35c3b2cb.png)  
  
- 아직 입양을 못 간 동물 중, 가장 오래 보호소에 있었던 동물 3마리의 이름과 보호 시작일을 조회하는 SQL문을 작성해주세요. 이때 결과는 보호 시작일 순으로 조회해야 합니다.  
  
  SELECT * FROM (  
                SELECT A.NAME   
                     , A.DATETIME   
                FROM ANIMAL_INS A  
                LEFT JOIN ANIMAL_OUTS B  
                ON A.ANIMAL_ID = B.ANIMAL_ID  
                WHERE B.ANIMAL_ID IS NULL  
                ORDER BY A.DATETIME)  
  WHERE ROWNUM < 4;  
                   
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124210575-9fbaed00-db26-11eb-8b74-bfb4631885b3.png)  
                   
- 보호소에서 중성화 수술을 거친 동물 정보를 알아보려 합니다. 보호소에 들어올 당시에는 중성화1되지 않았지만, 보호소를 나갈 당시에는 중성화된 동물의 아이디와 생물 종, 이름을 조회하는 아이디 순으로 조회하는 SQL 문을 작성해주세요.    
                   
  SELECT A.ANIMAL_ID  
       , A.ANIMAL_TYPE  
       , A.NAME  
  FROM ANIMAL_OUTS A  
  LEFT JOIN ANIMAL_INS B  
  ON A.ANIMAL_ID = B.ANIMAL_ID  
  WHERE B.SEX_UPON_INTAKE LIKE 'Intact%'  
      AND A.SEX_UPON_OUTCOME NOT LIKE 'Intact%'  
  ORDER BY A.ANIMAL_ID;  
                   
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124211970-02ad8380-db29-11eb-9262-10fef971b16c.png)  
</details>
<details>
  <summary>String, Date</summary>  
      
  📄 테이블    
  ![image](https://user-images.githubusercontent.com/73812196/124098265-5c656d80-da97-11eb-9ff1-465d9cb857f3.png)  
  ![image](https://user-images.githubusercontent.com/73812196/124202316-0afbc380-db15-11eb-873b-bdbd14ca7e30.png)  
      
- 동물 보호소에 들어온 동물 중 이름이 Lucy, Ella, Pickle, Rogan, Sabrina, Mitty인 동물의 아이디와 이름, 성별 및 중성화 여부를 조회하는 SQL 문을 작성해주세요.  
      
  SELECT ANIMAL_ID  
       , NAME  
       , SEX_UPON_INTAKE  
  FROM ANIMAL_INS  
  WHERE NAME IN ('Lucy', 'Ella', 'Pickle', 'Rogan', 'Sabrina', 'Mitty')  
  ORDER BY ANIMAL_ID;  
      
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124216854-19a4a380-db32-11eb-8712-c5bcee8d6bd3.png)  
      
- 보호소에 돌아가신 할머니가 기르던 개를 찾는 사람이 찾아왔습니다. 이 사람이 말하길 할머니가 기르던 개는 이름에 'el'이 들어간다고 합니다. 동물 보호소에 들어온 동물 이름 중, 이름에 "EL"이 들어가는 개의 아이디와 이름을 조회하는 SQL문을 작성해주세요. 이때 결과는 이름 순으로 조회해주세요. 단, 이름의 대소문자는 구분하지 않습니다.  
      
  SELECT ANIMAL_ID  
       , NAME  
  FROM ANIMAL_INS  
  WHERE UPPER(NAME) LIKE '%EL%'  
      AND ANIMAL_TYPE = 'Dog'  
  ORDER BY NAME;  
   
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124218538-60e06380-db35-11eb-9a0c-906930f249f8.png) 
      
- 보호소의 동물이 중성화되었는지 아닌지 파악하려 합니다. 중성화된 동물은 SEX_UPON_INTAKE 컬럼에 'Neutered' 또는 'Spayed'라는 단어가 들어있습니다. 동물의 아이디와 이름, 중성화 여부를 아이디 순으로 조회하는 SQL문을 작성해주세요. 이때 중성화가 되어있다면 'O', 아니라면 'X'라고 표시해주세요.  
      
  SELECT ANIMAL_ID  
       , NAME  
       , CASE WHEN SEX_UPON_INTAKE LIKE 'Neutered%' THEN 'O'  
              WHEN SEX_UPON_INTAKE LIKE 'Spayed%' THEN 'O'  
              ELSE 'X' END  
  FROM ANIMAL_INS  
  ORDER BY ANIMAL_ID  
      
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124221835-735d9b80-db3b-11eb-8330-f0c525431460.png)  
      
- 입양을 간 동물 중, 보호 기간이 가장 길었던 동물 두 마리의 아이디와 이름을 조회하는 SQL문을 작성해주세요. 이때 결과는 보호 기간이 긴 순으로 조회해야 합니다.    
  
  SELECT ANIMAL_ID  
       , NAME  
  FROM (SELECT A.ANIMAL_ID  
             , A.NAME  
        FROM ANIMAL_INS A  
        JOIN ANIMAL_OUTS B  
        ON A.ANIMAL_ID = B.ANIMAL_ID  
        ORDER BY B.DATETIME - A.DATETIME DESC  
       )  
  WHERE ROWNUM < 3;  
                   
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124223803-65aa1500-db3f-11eb-8a61-334f6af403a2.png)  
                   
- 테이블에 등록된 모든 레코드에 대해, 각 동물의 아이디와 이름, 들어온 날짜1를 조회하는 SQL문을 작성해주세요. 이때 결과는 아이디 순으로 조회해야 합니다.  
                   
  SELECT ANIMAL_ID  
       , NAME  
       , TO_CHAR(DATETIME, 'YYYY-MM-DD') AS 날짜  
  FROM ANIMAL_INS  
  ORDER BY ANIMAL_ID  
                   
  📄 결과  
  ![image](https://user-images.githubusercontent.com/73812196/124224411-90489d80-db40-11eb-9178-95c8dd038caa.png)   
</details>
