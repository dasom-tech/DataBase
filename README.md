# ๐ค SQL ๋ ๋ฒจ์!!
<details>
  <summary>๐ ์ฟผ๋ฆฌ ์ฐ์ต</summary>
<details>
  <summary>SELECT</summary>  
  
  ๐ ํ์ด๋ธ  
  ![image](https://user-images.githubusercontent.com/73812196/124098265-5c656d80-da97-11eb-9ff1-465d9cb857f3.png)
  
- ๋๋ฌผ ๋ณดํธ์์ ๋ค์ด์จ ๋ชจ๋  ๋๋ฌผ์ ์ ๋ณด๋ฅผ ANIMAL_ID์์ผ๋ก ์กฐํํ๋ SQL๋ฌธ์ ์์ฑํด์ฃผ์ธ์. SQL์ ์คํํ๋ฉด ๋ค์๊ณผ ๊ฐ์ด ์ถ๋ ฅ๋์ด์ผ ํฉ๋๋ค.  
  
  SELECT *  
  FROM ANIMAL_INS  
  ORDER BY ANIMAL_ID ASC;    
  
  ๐ ๊ฒฐ๊ณผ
  ![image](https://user-images.githubusercontent.com/73812196/124098315-68512f80-da97-11eb-8b3a-0eb25b5103a2.png)  
  
- ๋๋ฌผ ๋ณดํธ์์ ๋ค์ด์จ ๋ชจ๋  ๋๋ฌผ์ ์ด๋ฆ๊ณผ ๋ณดํธ ์์์ผ์ ์กฐํํ๋ SQL๋ฌธ์ ์์ฑํด์ฃผ์ธ์. ์ด๋ ๊ฒฐ๊ณผ๋ ANIMAL_ID ์ญ์์ผ๋ก ๋ณด์ฌ์ฃผ์ธ์. SQL์ ์คํํ๋ฉด ๋ค์๊ณผ ๊ฐ์ด ์ถ๋ ฅ๋์ด์ผ ํฉ๋๋ค.  
  
  SELECT NAME  
     , DATETIME  
  FROM ANIMAL_INS  
  ORDER BY ANIMAL_ID DESC;    
  
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124099277-515f0d00-da98-11eb-9e1e-97c0bf135f63.png)  
  
- ๋๋ฌผ ๋ณดํธ์์ ๋ค์ด์จ ๋๋ฌผ ์ค ์ํ ๋๋ฌผ1์ ์์ด๋์ ์ด๋ฆ์ ์กฐํํ๋ SQL ๋ฌธ์ ์์ฑํด์ฃผ์ธ์. ์ด๋ ๊ฒฐ๊ณผ๋ ์์ด๋ ์์ผ๋ก ์กฐํํด์ฃผ์ธ์.  
  
  SELECT ANIMAL_ID  
     , NAME  
  FROM ANIMAL_INS  
  WHERE INTAKE_CONDITION = 'Sick'  
  ORDER BY ANIMAL_ID ASC;    
  
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124099517-92572180-da98-11eb-98ef-2db44c947856.png)  
  
- ๋๋ฌผ ๋ณดํธ์์ ๋ค์ด์จ ๋๋ฌผ ์ค ์ ์ ๋๋ฌผ1์ ์์ด๋์ ์ด๋ฆ์ ์กฐํํ๋ SQL ๋ฌธ์ ์์ฑํด์ฃผ์ธ์. ์ด๋ ๊ฒฐ๊ณผ๋ ์์ด๋ ์์ผ๋ก ์กฐํํด์ฃผ์ธ์.  
  
  SELECT ANIMAL_ID  
       , NAME  
  FROM ANIMAL_INS  
  WHERE INTAKE_CONDITION NOT IN 'Aged'  
  ORDER BY ANIMAL_ID ASC;    
  
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124099654-b9155800-da98-11eb-97a6-3c220c2b227e.png)  
  
- ๋๋ฌผ ๋ณดํธ์์ ๋ค์ด์จ ๋ชจ๋  ๋๋ฌผ์ ์์ด๋์ ์ด๋ฆ, ๋ณดํธ ์์์ผ์ ์ด๋ฆ ์์ผ๋ก ์กฐํํ๋ SQL๋ฌธ์ ์์ฑํด์ฃผ์ธ์. ๋จ, ์ด๋ฆ์ด ๊ฐ์ ๋๋ฌผ ์ค์์๋ ๋ณดํธ๋ฅผ ๋์ค์ ์์ํ ๋๋ฌผ์ ๋จผ์  ๋ณด์ฌ์ค์ผ ํฉ๋๋ค.  
  
  SELECT ANIMAL_ID  
     , NAME  
     , DATETIME  
  FROM ANIMAL_INS  
  ORDER BY NAME ASC, DATETIME DESC;    
  
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124099909-ecf07d80-da98-11eb-8d4f-18f70489fc13.png)  
  
- ๋๋ฌผ ๋ณดํธ์์ ๊ฐ์ฅ ๋จผ์  ๋ค์ด์จ ๋๋ฌผ์ ์ด๋ฆ์ ์กฐํํ๋ SQL ๋ฌธ์ ์์ฑํด์ฃผ์ธ์.  
  
  SELECT NAME  
  FROM ANIMAL_INS  
  WHERE DATETIME = (SELECT MIN(DATETIME)  
                    FROM ANIMAL_INS);    
  
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124100042-13161d80-da99-11eb-915e-c0e0a0c2cbd7.png)  
</details>  
<details>
  <summary>SUM, MAX, MIN</summary>  
  
  ๐ ํ์ด๋ธ    
  ![image](https://user-images.githubusercontent.com/73812196/124098265-5c656d80-da97-11eb-9ff1-465d9cb857f3.png)  
  
- ๊ฐ์ฅ ์ต๊ทผ์ ๋ค์ด์จ ๋๋ฌผ์ ์ธ์  ๋ค์ด์๋์ง ์กฐํํ๋ SQL ๋ฌธ์ ์์ฑํด์ฃผ์ธ์.  
  
  SELECT MAX(DATETIME)  
  FROM ANIMAL_INS;  
  
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124201699-a0965380-db13-11eb-8269-f05c6365beda.png)  
  
- ๋๋ฌผ ๋ณดํธ์์ ๊ฐ์ฅ ๋จผ์  ๋ค์ด์จ ๋๋ฌผ์ ์ธ์  ๋ค์ด์๋์ง ์กฐํํ๋ SQL ๋ฌธ์ ์์ฑํด์ฃผ์ธ์.  
  
  SELECT MIN(DATETIME)  
  FROM ANIMAL_INS;  
  
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124201762-c6235d00-db13-11eb-9456-23eec846f1c5.png)  
  
- ๋๋ฌผ ๋ณดํธ์์ ๋๋ฌผ์ด ๋ช ๋ง๋ฆฌ ๋ค์ด์๋์ง ์กฐํํ๋ SQL ๋ฌธ์ ์์ฑํด์ฃผ์ธ์.  
  
  SELECT COUNT(ANIMAL_ID)  
  FROM ANIMAL_INS;  
  
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124201803-e8b57600-db13-11eb-80c0-3cfe9c8defd6.png)  
  
- ๋๋ฌผ ๋ณดํธ์์ ๋ค์ด์จ ๋๋ฌผ์ ์ด๋ฆ์ ๋ช ๊ฐ์ธ์ง ์กฐํํ๋ SQL ๋ฌธ์ ์์ฑํด์ฃผ์ธ์. ์ด๋ ์ด๋ฆ์ด NULL์ธ ๊ฒฝ์ฐ๋ ์ง๊ณํ์ง ์์ผ๋ฉฐ ์ค๋ณต๋๋ ์ด๋ฆ์ ํ๋๋ก ์นฉ๋๋ค.
  
  SELECT COUNT(DISTINCT(NAME))  
  FROM ANIMAL_INS  
  WHERE NAME NOT IN('NULL'); 
  
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124201858-169aba80-db14-11eb-8f47-40a95c6dda4f.png)  
</details>  
<details>
  <summary>GROUP BY, HAVING</summary>  
  
  ๐ ํ์ด๋ธ  
  ![image](https://user-images.githubusercontent.com/73812196/124098265-5c656d80-da97-11eb-9ff1-465d9cb857f3.png)  
  
- ๋๋ฌผ ๋ณดํธ์์ ๋ค์ด์จ ๋๋ฌผ ์ค ๊ณ ์์ด์ ๊ฐ๊ฐ ๊ฐ๊ฐ ๋ช ๋ง๋ฆฌ์ธ์ง ์กฐํํ๋ SQL๋ฌธ์ ์์ฑํด์ฃผ์ธ์. ์ด๋ ๊ณ ์์ด๋ฅผ ๊ฐ๋ณด๋ค ๋จผ์  ์กฐํํด์ฃผ์ธ์.  
  
  SELECT ANIMAL_TYPE  
     , COUNT(ANIMAL_ID) AS count  
  FROM ANIMAL_INS  
  GROUP BY ANIMAL_TYPE  
  ORDER BY ANIMAL_TYPE ASC;  
  
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124202093-9b85d400-db14-11eb-9391-bbf67116756c.png)  
  
- ๋๋ฌผ ๋ณดํธ์์ ๋ค์ด์จ ๋๋ฌผ ์ด๋ฆ ์ค ๋ ๋ฒ ์ด์ ์ฐ์ธ ์ด๋ฆ๊ณผ ํด๋น ์ด๋ฆ์ด ์ฐ์ธ ํ์๋ฅผ ์กฐํํ๋ SQL๋ฌธ์ ์์ฑํด์ฃผ์ธ์. ์ด๋ ๊ฒฐ๊ณผ๋ ์ด๋ฆ์ด ์๋ ๋๋ฌผ์ ์ง๊ณ์์ ์ ์ธํ๋ฉฐ, ๊ฒฐ๊ณผ๋ ์ด๋ฆ ์์ผ๋ก ์กฐํํด์ฃผ์ธ์.  
  
  SELECT NAME  
     , COUNT(NAME) AS count  
  FROM ANIMAL_INS  
  GROUP BY NAME HAVING COUNT(NAME) >= 2  
  ORDER BY NAME ASC; 
  
  ๐ ๊ฒฐ๊ณผ    
  ![image](https://user-images.githubusercontent.com/73812196/124202169-ccfe9f80-db14-11eb-804b-8a54b23d98e8.png)  
  
  ๐ ํ์ด๋ธ  
  ![image](https://user-images.githubusercontent.com/73812196/124202316-0afbc380-db15-11eb-873b-bdbd14ca7e30.png)  
  
- ๋ณดํธ์์์๋ ๋ช ์์ ์์์ด ๊ฐ์ฅ ํ๋ฐํ๊ฒ ์ผ์ด๋๋์ง ์์๋ณด๋ ค ํฉ๋๋ค. 09:00๋ถํฐ 19:59๊น์ง, ๊ฐ ์๊ฐ๋๋ณ๋ก ์์์ด ๋ช ๊ฑด์ด๋ ๋ฐ์ํ๋์ง ์กฐํํ๋ SQL๋ฌธ์ ์์ฑํด์ฃผ์ธ์. ์ด๋ ๊ฒฐ๊ณผ๋ ์๊ฐ๋ ์์ผ๋ก ์ ๋ ฌํด์ผ ํฉ๋๋ค.  
  
  SELECT EXTRACT(HOUR FROM CAST(DATETIME AS TIMESTAMP)) AS HOUR  
     , COUNT(ANIMAL_ID) AS COUNT  
  FROM ANIMAL_OUTS A  
  WHERE EXTRACT(HOUR FROM CAST(DATETIME AS TIMESTAMP)) BETWEEN 9 AND 19  
  GROUP BY EXTRACT(HOUR FROM CAST(DATETIME AS TIMESTAMP))  
  ORDER BY HOUR;  
  
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124202400-39799e80-db15-11eb-8ac3-99b6adf990e2.png)  
  
- ๋ณดํธ์์์๋ ๋ช ์์ ์์์ด ๊ฐ์ฅ ํ๋ฐํ๊ฒ ์ผ์ด๋๋์ง ์์๋ณด๋ ค ํฉ๋๋ค. 0์๋ถํฐ 23์๊น์ง, ๊ฐ ์๊ฐ๋๋ณ๋ก ์์์ด ๋ช ๊ฑด์ด๋ ๋ฐ์ํ๋์ง ์กฐํํ๋ SQL๋ฌธ์ ์์ฑํด์ฃผ์ธ์. ์ด๋ ๊ฒฐ๊ณผ๋ ์๊ฐ๋ ์์ผ๋ก ์ ๋ ฌํด์ผ ํฉ๋๋ค.  
  
  SELECT HOUR, COUNT(B.DATETIME) AS COUNT  
  FROM  
     (SELECT LEVEL-1 AS HOUR --LEVEL์ ๊ธฐ๋ณธ์ผ๋ก 1๋ถํฐ ์์  
      FROM DUAL    
      CONNECT BY LEVEL<25) A   
  LEFT JOIN ANIMAL_OUTS B --๋ฐ์ดํฐ๊ฐ ์์ด๋ ์ถ๋ ฅ๋์ด์ผ ํ๋ฏ๋ก LEFT JOIN  
  ON A.HOUR = TO_CHAR(B.DATETIME,'HH24')  
  GROUP BY HOUR   
  ORDER BY HOUR;  
                           
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124205529-61203500-db1c-11eb-8c32-b00efec820bf.png)   
</details>
<details>
  <summary>IS NULL</summary>  
  
  ๐ ํ์ด๋ธ  
  ![image](https://user-images.githubusercontent.com/73812196/124098265-5c656d80-da97-11eb-9ff1-465d9cb857f3.png)  
  
- ๋๋ฌผ ๋ณดํธ์์ ๋ค์ด์จ ๋๋ฌผ ์ค, ์ด๋ฆ์ด ์๋ ์ฑ๋ก ๋ค์ด์จ ๋๋ฌผ์ ID๋ฅผ ์กฐํํ๋ SQL ๋ฌธ์ ์์ฑํด์ฃผ์ธ์. ๋จ, ID๋ ์ค๋ฆ์ฐจ์ ์ ๋ ฌ๋์ด์ผ ํฉ๋๋ค.  
  
  SELECT ANIMAL_ID
  FROM ANIMAL_INS
  WHERE NAME IS NULL
  ORDER BY ANIMAL_ID;  
  
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124206008-6a5dd180-db1d-11eb-9d57-bd5054d82f91.png)  
  
- ๋๋ฌผ ๋ณดํธ์์ ๋ค์ด์จ ๋๋ฌผ ์ค, ์ด๋ฆ์ด ์๋ ๋๋ฌผ์ ID๋ฅผ ์กฐํํ๋ SQL ๋ฌธ์ ์์ฑํด์ฃผ์ธ์. ๋จ, ID๋ ์ค๋ฆ์ฐจ์ ์ ๋ ฌ๋์ด์ผ ํฉ๋๋ค.  
  
  SELECT ANIMAL_ID  
  FROM ANIMAL_INS  
  WHERE NAME IS NOT NULL  
  ORDER BY ANIMAL_ID;  
  
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124206192-d3dde000-db1d-11eb-84c1-238d06cab297.png)  
  
- ์์ ๊ฒ์ํ์ ๋๋ฌผ ์ ๋ณด๋ฅผ ๊ฒ์ํ๋ ค ํฉ๋๋ค. ๋๋ฌผ์ ์๋ฌผ ์ข, ์ด๋ฆ, ์ฑ๋ณ ๋ฐ ์ค์ฑํ ์ฌ๋ถ๋ฅผ ์์ด๋ ์์ผ๋ก ์กฐํํ๋ SQL๋ฌธ์ ์์ฑํด์ฃผ์ธ์. ์ด๋ ํ๋ก๊ทธ๋๋ฐ์ ๋ชจ๋ฅด๋ ์ฌ๋๋ค์ NULL์ด๋ผ๋ ๊ธฐํธ๋ฅผ ๋ชจ๋ฅด๊ธฐ ๋๋ฌธ์, ์ด๋ฆ์ด ์๋ ๋๋ฌผ์ ์ด๋ฆ์ "No name"์ผ๋ก ํ์ํด ์ฃผ์ธ์.  
  
  SELECT ANIMAL_TYPE  
       , NVL(NAME, 'No name')  
       , SEX_UPON_INTAKE  
  FROM ANIMAL_INS  
  ORDER BY ANIMAL_ID;  
  
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124207379-57003580-db20-11eb-99a9-14989eb3bfc7.png)  
  ![image](https://user-images.githubusercontent.com/73812196/124207410-6b443280-db20-11eb-9273-172e2053b80a.png)  
</details> 

<details>
  <summary>JOIN</summary>
  
  ๐ ํ์ด๋ธ  
  ![image](https://user-images.githubusercontent.com/73812196/124098265-5c656d80-da97-11eb-9ff1-465d9cb857f3.png)  
  ![image](https://user-images.githubusercontent.com/73812196/124202316-0afbc380-db15-11eb-873b-bdbd14ca7e30.png)  
  
- ANIMAL_OUTS ํ์ด๋ธ์ ๋๋ฌผ ๋ณดํธ์์์ ์์ ๋ณด๋ธ ๋๋ฌผ์ ์ ๋ณด๋ฅผ ๋ด์ ํ์ด๋ธ์๋๋ค. ANIMAL_OUTS ํ์ด๋ธ์ ANIMAL_ID๋ ANIMAL_INS์ ANIMAL_ID์ ์ธ๋ ํค์๋๋ค. ์ฒ์ฌ์ง๋ณ์ผ๋ก ์ธํด ์ผ๋ถ ๋ฐ์ดํฐ๊ฐ ์ ์ค๋์์ต๋๋ค. ์์์ ๊ฐ ๊ธฐ๋ก์ ์๋๋ฐ, ๋ณดํธ์์ ๋ค์ด์จ ๊ธฐ๋ก์ด ์๋ ๋๋ฌผ์ ID์ ์ด๋ฆ์ ID ์์ผ๋ก ์กฐํํ๋ SQL๋ฌธ์ ์์ฑํด์ฃผ์ธ์.  
  
  SELECT A.ANIMAL_ID  
       , A.NAME  
  FROM ANIMAL_OUTS A  
  LEFT JOIN ANIMAL_INS B  
  ON A.ANIMAL_ID = B.ANIMAL_ID  
  WHERE B.ANIMAL_ID IS NULL  
  ORDER BY A.ANIMAL_ID;   
  
  ๐ ๊ฒฐ๊ณผ   
  ![image](https://user-images.githubusercontent.com/73812196/124208601-d3941380-db22-11eb-98fa-86fe80c7ca4d.png)  
  
- ๊ด๋ฆฌ์์ ์ค์๋ก ์ผ๋ถ ๋๋ฌผ์ ์์์ผ์ด ์๋ชป ์๋ ฅ๋์์ต๋๋ค. ๋ณดํธ ์์์ผ๋ณด๋ค ์์์ผ์ด ๋ ๋น ๋ฅธ ๋๋ฌผ์ ์์ด๋์ ์ด๋ฆ์ ์กฐํํ๋ SQL๋ฌธ์ ์์ฑํด์ฃผ์ธ์. ์ด๋ ๊ฒฐ๊ณผ๋ ๋ณดํธ ์์์ผ์ด ๋น ๋ฅธ ์์ผ๋ก ์กฐํํด์ผํฉ๋๋ค.  
  
  SELECT A.ANIMAL_ID  
       , A.NAME  
  FROM ANIMAL_INS A  
  FULL OUTER JOIN ANIMAL_OUTS B  
  ON A.ANIMAL_ID = B.ANIMAL_ID  
  WHERE A.DATETIME > B.DATETIME  
  ORDER BY A.DATETIME;  
  
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124208980-b449b600-db23-11eb-9d8e-765e35c3b2cb.png)  
  
- ์์ง ์์์ ๋ชป ๊ฐ ๋๋ฌผ ์ค, ๊ฐ์ฅ ์ค๋ ๋ณดํธ์์ ์์๋ ๋๋ฌผ 3๋ง๋ฆฌ์ ์ด๋ฆ๊ณผ ๋ณดํธ ์์์ผ์ ์กฐํํ๋ SQL๋ฌธ์ ์์ฑํด์ฃผ์ธ์. ์ด๋ ๊ฒฐ๊ณผ๋ ๋ณดํธ ์์์ผ ์์ผ๋ก ์กฐํํด์ผ ํฉ๋๋ค.  
  
  SELECT * FROM (  
                SELECT A.NAME   
                     , A.DATETIME   
                FROM ANIMAL_INS A  
                LEFT JOIN ANIMAL_OUTS B  
                ON A.ANIMAL_ID = B.ANIMAL_ID  
                WHERE B.ANIMAL_ID IS NULL  
                ORDER BY A.DATETIME)  
  WHERE ROWNUM < 4;  
                   
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124210575-9fbaed00-db26-11eb-8b74-bfb4631885b3.png)  
                   
- ๋ณดํธ์์์ ์ค์ฑํ ์์ ์ ๊ฑฐ์น ๋๋ฌผ ์ ๋ณด๋ฅผ ์์๋ณด๋ ค ํฉ๋๋ค. ๋ณดํธ์์ ๋ค์ด์ฌ ๋น์์๋ ์ค์ฑํ1๋์ง ์์์ง๋ง, ๋ณดํธ์๋ฅผ ๋๊ฐ ๋น์์๋ ์ค์ฑํ๋ ๋๋ฌผ์ ์์ด๋์ ์๋ฌผ ์ข, ์ด๋ฆ์ ์กฐํํ๋ ์์ด๋ ์์ผ๋ก ์กฐํํ๋ SQL ๋ฌธ์ ์์ฑํด์ฃผ์ธ์.    
                   
  SELECT A.ANIMAL_ID  
       , A.ANIMAL_TYPE  
       , A.NAME  
  FROM ANIMAL_OUTS A  
  LEFT JOIN ANIMAL_INS B  
  ON A.ANIMAL_ID = B.ANIMAL_ID  
  WHERE B.SEX_UPON_INTAKE LIKE 'Intact%'  
      AND A.SEX_UPON_OUTCOME NOT LIKE 'Intact%'  
  ORDER BY A.ANIMAL_ID;  
                   
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124211970-02ad8380-db29-11eb-9262-10fef971b16c.png)  
</details>
<details>
  <summary>String, Date</summary>  
      
  ๐ ํ์ด๋ธ    
  ![image](https://user-images.githubusercontent.com/73812196/124098265-5c656d80-da97-11eb-9ff1-465d9cb857f3.png)  
  ![image](https://user-images.githubusercontent.com/73812196/124202316-0afbc380-db15-11eb-873b-bdbd14ca7e30.png)  
      
- ๋๋ฌผ ๋ณดํธ์์ ๋ค์ด์จ ๋๋ฌผ ์ค ์ด๋ฆ์ด Lucy, Ella, Pickle, Rogan, Sabrina, Mitty์ธ ๋๋ฌผ์ ์์ด๋์ ์ด๋ฆ, ์ฑ๋ณ ๋ฐ ์ค์ฑํ ์ฌ๋ถ๋ฅผ ์กฐํํ๋ SQL ๋ฌธ์ ์์ฑํด์ฃผ์ธ์.  
      
  SELECT ANIMAL_ID  
       , NAME  
       , SEX_UPON_INTAKE  
  FROM ANIMAL_INS  
  WHERE NAME IN ('Lucy', 'Ella', 'Pickle', 'Rogan', 'Sabrina', 'Mitty')  
  ORDER BY ANIMAL_ID;  
      
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124216854-19a4a380-db32-11eb-8712-c5bcee8d6bd3.png)  
      
- ๋ณดํธ์์ ๋์๊ฐ์  ํ ๋จธ๋๊ฐ ๊ธฐ๋ฅด๋ ๊ฐ๋ฅผ ์ฐพ๋ ์ฌ๋์ด ์ฐพ์์์ต๋๋ค. ์ด ์ฌ๋์ด ๋งํ๊ธธ ํ ๋จธ๋๊ฐ ๊ธฐ๋ฅด๋ ๊ฐ๋ ์ด๋ฆ์ 'el'์ด ๋ค์ด๊ฐ๋ค๊ณ  ํฉ๋๋ค. ๋๋ฌผ ๋ณดํธ์์ ๋ค์ด์จ ๋๋ฌผ ์ด๋ฆ ์ค, ์ด๋ฆ์ "EL"์ด ๋ค์ด๊ฐ๋ ๊ฐ์ ์์ด๋์ ์ด๋ฆ์ ์กฐํํ๋ SQL๋ฌธ์ ์์ฑํด์ฃผ์ธ์. ์ด๋ ๊ฒฐ๊ณผ๋ ์ด๋ฆ ์์ผ๋ก ์กฐํํด์ฃผ์ธ์. ๋จ, ์ด๋ฆ์ ๋์๋ฌธ์๋ ๊ตฌ๋ถํ์ง ์์ต๋๋ค.  
      
  SELECT ANIMAL_ID  
       , NAME  
  FROM ANIMAL_INS  
  WHERE UPPER(NAME) LIKE '%EL%'  
      AND ANIMAL_TYPE = 'Dog'  
  ORDER BY NAME;  
   
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124218538-60e06380-db35-11eb-9a0c-906930f249f8.png) 
      
- ๋ณดํธ์์ ๋๋ฌผ์ด ์ค์ฑํ๋์๋์ง ์๋์ง ํ์ํ๋ ค ํฉ๋๋ค. ์ค์ฑํ๋ ๋๋ฌผ์ SEX_UPON_INTAKE ์ปฌ๋ผ์ 'Neutered' ๋๋ 'Spayed'๋ผ๋ ๋จ์ด๊ฐ ๋ค์ด์์ต๋๋ค. ๋๋ฌผ์ ์์ด๋์ ์ด๋ฆ, ์ค์ฑํ ์ฌ๋ถ๋ฅผ ์์ด๋ ์์ผ๋ก ์กฐํํ๋ SQL๋ฌธ์ ์์ฑํด์ฃผ์ธ์. ์ด๋ ์ค์ฑํ๊ฐ ๋์ด์๋ค๋ฉด 'O', ์๋๋ผ๋ฉด 'X'๋ผ๊ณ  ํ์ํด์ฃผ์ธ์.  
      
  SELECT ANIMAL_ID  
       , NAME  
       , CASE WHEN SEX_UPON_INTAKE LIKE 'Neutered%' THEN 'O'  
              WHEN SEX_UPON_INTAKE LIKE 'Spayed%' THEN 'O'  
              ELSE 'X' END  
  FROM ANIMAL_INS  
  ORDER BY ANIMAL_ID  
      
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124221835-735d9b80-db3b-11eb-8330-f0c525431460.png)  
      
- ์์์ ๊ฐ ๋๋ฌผ ์ค, ๋ณดํธ ๊ธฐ๊ฐ์ด ๊ฐ์ฅ ๊ธธ์๋ ๋๋ฌผ ๋ ๋ง๋ฆฌ์ ์์ด๋์ ์ด๋ฆ์ ์กฐํํ๋ SQL๋ฌธ์ ์์ฑํด์ฃผ์ธ์. ์ด๋ ๊ฒฐ๊ณผ๋ ๋ณดํธ ๊ธฐ๊ฐ์ด ๊ธด ์์ผ๋ก ์กฐํํด์ผ ํฉ๋๋ค.    
  
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
                   
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124223803-65aa1500-db3f-11eb-8a61-334f6af403a2.png)  
                   
- ํ์ด๋ธ์ ๋ฑ๋ก๋ ๋ชจ๋  ๋ ์ฝ๋์ ๋ํด, ๊ฐ ๋๋ฌผ์ ์์ด๋์ ์ด๋ฆ, ๋ค์ด์จ ๋ ์ง1๋ฅผ ์กฐํํ๋ SQL๋ฌธ์ ์์ฑํด์ฃผ์ธ์. ์ด๋ ๊ฒฐ๊ณผ๋ ์์ด๋ ์์ผ๋ก ์กฐํํด์ผ ํฉ๋๋ค.  
                   
  SELECT ANIMAL_ID  
       , NAME  
       , TO_CHAR(DATETIME, 'YYYY-MM-DD') AS ๋ ์ง  
  FROM ANIMAL_INS  
  ORDER BY ANIMAL_ID  
                   
  ๐ ๊ฒฐ๊ณผ  
  ![image](https://user-images.githubusercontent.com/73812196/124224411-90489d80-db40-11eb-9178-95c8dd038caa.png)   
</details>
</details>  
      
## ๐ SELECT ์ฟผ๋ฆฌ๋ฌธ ์คํ์ ์์   
      FROM -> WHERE -> GROUP BY -> HAVING -> SELECT -> ORDER BY   
<details>
  <summary>๐ ๋ฐ์ดํฐ๋ฒ ์ด์ค ๊ฐ์ฒด </summary>

### ๐ฉ ๊ฐ์
 - ํ์ด๋ธ : ๋ฐ์ดํฐ๋ฅผ ๋ด๊ณ  ์๋ ๊ฐ์ฒด
 - ๋ทฐ : ํ๋ ์ด์์ ํ์ด๋ธ์ ์ฐ๊ฒฐํด ๋ง์น ํ์ด๋ธ์ธ ๊ฒ์ฒ๋ผ ์ฌ์ฉํ๋ ๊ฐ์ฒด
 - ์ธ๋ฑ์ค : ํ์ด๋ธ์ ์๋ ๋ฐ์ดํฐ๋ฅผ ๋น ๋ฅด๊ฒ ์ฐพ๊ธฐ ์ํ ๊ฐ์ฒด
 - ์๋ธ๋ : ๋ฐ์ดํฐ๋ฒ ์ด์ค ๊ฐ์ฒด์ ๋ํ ๋ณ์นญ์ ๋ถ์ฌํ ๊ฐ์ฒด
 - ์ํ์ค : ์ผ๋ จ๋ฒํธ ์ฑ๋ฒ์ ํ  ๋ ์ฌ์ฉ๋๋ ๊ฐ์ฒด
 - ํจ์ : ํน์  ์ฐ์ฐ์ ํ๊ณ  ๊ฐ์ ๋ฐํํ๋ ๊ฐ์ฒด
 - ํ๋ก์์  : ํจ์์ ๋น์ทํ์ง๋ง ๊ฐ์ ๋ฐํํ์ง๋ ์๋ ๊ฐ์ฒด
 - ํจํค์ง : ์ฉ๋์ ๋ง๊ฒ ํจ์๋ ํ๋ก์์ ๋ฅผ ํ๋๋ก ๋ฌถ์ด ๋์ ๊ฐ์ฒด  
 
### ๐ฉ ํ์ด๋ธ
 - ํ์ด๋ธ ์์ฑ    
   CREATE TABLE ํ์ด๋ธ๋ช (    
   ์ปฌ๋ผ1 ๋ฐ์ดํฐํ์ [NULL, NOT NULL],    
   ์ปฌ๋ผ2 ๋ฐ์ดํฐํ์ [NULL, NOT NULL],    
   ...      
   );    
   
 - ๋ฐ์ดํฐ ํ์    
   1. CHAR : ๊ณ ์ ๊ธธ์ด, ์ต๋ 2000byte  
   2. VARCHAR2 : ๊ฐ๋ณ๊ธธ์ด, ์ต๋ 4000byte, ์ ์ฅ ๊ณต๊ฐ์ ์ํด CHAR๋ณด๋ค๋ VARCHAR2๋ฅผ ์ฌ์ฉํ  ๊ฒ  
   3. NCHAR : ๊ณ ์ ๊ธธ์ด ์ ๋์ฝ๋ ๋ฌธ์(๋ค๊ตญ์ด ์๋ ฅ ๊ฐ๋ฅ), ์ต๋ 2000vyte  
   4. NVARCHAR2 : ๊ฐ๋ณ๊ธธ์ด ์ ๋์ฝ๋ ๋ฌธ์(๋ค๊ตญ์ด ์๋ ฅ ๊ฐ๋ฅ), ์ต๋ 4000byte, ์์ด ํ ๋ฌธ์ : 1byte, ํ๊ธ : 2byte  
   5. NUMBER : ๊ฐ๋ณ์ซ์, ์ต๋ 22byte
   6. FLOAT : NUMBER์ ํ์ ํ์, ์ต๋ 22byte, ์ด์ง์ ๊ธฐ์ค
   7. BINARY_FLOAT : 32๋นํธ ๋ถ๋์์์  ์, ์ต๋ 4byte
   8. BINARY_DOUBLE : 64๋นํธ ๋ถ๋์์์  ์, ์ต๋ 8byte  
   9. DATE : ์ฐ,์,์ผ,์,๋ถ,์ด๊น์ง ์๋ ฅ ๊ฐ๋ฅ  
   10. TIMESTAMP : ๋ฐ๋ฆฌ์ด๊น์ง ์๋ ฅ ๊ฐ๋ฅ  
   11. CLOB :  ๋ฌธ์ํ ๋์ฉ๋ ๊ฐ์ฒด, ๊ณ ์ ๊ธธ์ด์ ๊ฐ๋ณ๊ธธ์ด ๋ฌธ์ ์งํฉ ์ง์, ๋ฌธ์ํ ๋์ฉ๋ ๋ฐ์ดํฐ ์ ์ฅ์    
   12. NCLOB : ์ ๋์ฝ๋๋ฅผ ํฌํจํ ๋ฌธ์ํ ๋์ฉ๋ ๊ฐ์ฒด, ๋ฌธ์ํ ๋์ฉ๋ ๋ฐ์ดํฐ ์ ์ฅ์    
   13. BLOB : ์ด์งํ ๋์ฉ๋ ๊ฐ์ฒด, ๊ทธ๋ํฝ, ์ด๋ฏธ์ง, ๋์์ ๋ฑ  
   14. BFILE : ๋์ฉ๋ ์ด์ง ํ์ผ์ ๋ํ ๋ก์ผ์ดํฐ(์์น, ์ด๋ฆ) ์ ์ฅ
   
 - ์ ์ฝ์กฐ๊ฑด  
   1. NOT NULL : NULL ํ์ฉํ์ง ์์. ๋ฐ๋์ ๋ฐ์ดํฐ๋ฅผ ์๋ ฅํด์ผ ํจ
   2. UNIQUE : ์ค๋ณต ํ์ฉํ์ง ์์. UNIQUE ๋น๊ต ๋์์์ NULL์ ์ ์ธ๋จ
   3. Primary key : ๊ธฐ๋ณธํค(NOT NULL+UNIQUE), ํ์ด๋ธ๋น 1๊ฐ ์์ฑ ๊ฐ๋ฅ, ๋ฐ์ดํฐ ๋ฌด๊ฒฐ์ฑ์ ์ค์ง์ ์ผ๋ก ๊ตฌํํ ๊ฒ, ํน์ํ ๊ฒฝ์ฐ๋ฅผ ์ ์ธํ๊ณ  ๊ธฐ๋ณธํค๋ ๋ฐ๋์ ์์ฑํ๋ ๊ฒ์ด ์์น
   4. Foreign key : ์ธ๋ํค, ์ฌ๋ฌ ์ปฌ๋ผ์ ์ธ๋ํค๋ก ๋ง๋๋ ค๋ฉด ์ฐธ์กฐํ๋ ์ปฌ๋ผ๊ณผ ์ธ๋ํค ์ปฌ๋ผ์ ์์์ ๊ฐ์๋ ๊ฐ์์ผ ํจ
   5. CHECK : ์ปฌ๋ผ์ ์๋ ฅ๋๋ ๋ฐ์ดํฐ๋ฅผ ์ฒดํฌํด ํน์  ์กฐ๊ฑด์ ๋ง๋ ๋ฐ์ดํฐ๋ง ์๋ ฅ ๋ฐ๊ณ  ๊ทธ๋ ์ง ์์ผ๋ฉด ์ค๋ฅ๋ฅผ ๋ฑ์ด ๋  
   6. DEFAULT : ์ ์ฝ์กฐ๊ฑด์ ์๋๋ ์ปฌ๋ผ ์์ฑ ์ค ํ๋๋ก ์ปฌ๋ผ ์์ฑ์ ์๋์ผ๋ก ๋ํดํธ ๊ฐ์ด ๋ค์ด๊ฐ  
      ex) ํ์ด๋ธ ์์ฑ์   
          ์ปฌ๋ผ๋ช DATE DEFAULT SYSDATE  
          INSERT INTO ํ์ด๋ธ๋ช(์ปฌ๋ผ1, ์ปฌ๋ผ2) VALUES ('AA', 'BB');  
          ๊ฒฐ๊ณผ:    
          AA   BB   2021/07/05 10:12:10  
          
 - ํ์ด๋ธ ์ญ์     
   DROP TABLE ํ์ด๋ธ๋ช [CASCADE CONSTRAINTS] : CASCADE CONSTRAINTS๋ฅผ ๋ถ์ด๋ฉด ๊ธฐ๋ณธํค, ์ ์ฝ์กฐ๊ฑด ๋ฑ๋ ์๋ ์ญ์ ๋จ  
   
 - ํ์ด๋ธ ๋ณ๊ฒฝ  
   ALTER TABLE ํ์ด๋ธ๋ช RENAME COLUMN ๋ณ๊ฒฝ์ ์ปฌ๋ผ๋ช TO ๋ณ๊ฒฝํ์ปฌ๋ผ๋ช;  
   ALTER TABLE ํ์ด๋ธ๋ช MODIFY ์ปฌ๋ผ๋ช ๋ฐ์ดํฐํ์;
   ALTER TABLE ํ์ด๋ธ๋ช ADD ์ปฌ๋ผ๋ช ๋ฐ์ดํฐํ์;
   ALTER TABLE ํ์ด๋ธ๋ช DROP COLUMN ์ปฌ๋ผ๋ช;
   ALTER TABLE ํ์ด๋ธ๋ช ADD CONSTRAINTS ์ ์ฝ์กฐ๊ฑด๋ช PRIMARY KEY(์ปฌ๋ผ๋ช, ..);
   ALTER TABLE ํ์ด๋ธ๋ช DROP CONSTRAINS ์ ์ฝ์กฐ๊ฑด๋ช;  
   
 - ํ์ด๋ธ ๋ณต์ฌ  
   CREATE TABLE ํ์ด๋ธ๋ช AS  
   SELECT ์ปฌ๋ผ1, ์ปฌ๋ผ2, ...  
   FROM ๋ณต์ฌํ  ํ์ด๋ธ๋ช;  
   
### ๐ฉ ๋ทฐ  
 - ๋ทฐ ์์ฑ  
   CREATE OR REPLACE VIEW ๋ทฐ๋ช AS
   SELECT ๋ฌธ์ฅ;  
   ex) CREATE OR REPLACE VIEW ๋ทฐ๋ช AS  
       SELECT a.employee_id, a.emp_name, a.department_id, b.department_name  
       FROM employee a, departments b  
       WHERE a.department_id = b.department_id;  
      
 - ๋ทฐ ์ญ์   
   DROP VIEW ๋ทฐ๋ช;  
      
### ๐ฉ ์ธ๋ฑ์ค    
 - ์ธ๋ฑ์ค ์์ฑ : UNIQUE ์ ์ฝ์กฐ๊ฑด์ ๋ง๋ค๋ฉด ์๋์ผ๋ก UNIQUE ์ธ๋ฑ์ค๋ฅผ ์์ฑํด ์ค  
   CREATE[UNIQUE] INDEX ์ธ๋ฑ์ค๋ช  
   ON ํ์ด๋ธ๋ช(์ปฌ๋ผ1, ์ปฌ๋ผ2, ...);  
      
 - ์ผ๋ฐ์ ์ผ๋ก ํ์ด๋ธ ์ ์ฒด row ์์ 15% ์ดํ์ ๋ฐ์ดํฐ๋ฅผ ์กฐํํ  ๋ ์ธ๋ฑ์ค ์์ฑ
 - ํ์ด๋ธ ๊ฑด์๊ฐ ์ ๋ค๋ฉด ๊ตณ์ด ๋ง๋ค ํ์ ์์
 - ๋ฐ์ดํฐ์ ์ ์ผ์ฑ ์ ๋๊ฐ ์ข๊ฑฐ๋ ๋ฒ์๊ฐ ๋์ ๊ฐ์ ๊ฐ์ง ์ปฌ๋ผ์ ์ธ๋ฑ์ค๋ก ๋ง๋๋ ๊ฒ์ด ์ข์
 - NULL์ด ๋ง์ด ํฌํจ๋ ์ปฌ๋ผ์ ์ธ๋ฑ์ค ์ปฌ๋ผ์ผ๋ก ๋ง๋ค๊ธฐ ์ ๋น์น ์์
 - ๊ฒฐํฉ ์ธ๋ฑ์ค๋ฅผ ๋ง๋ค ๋๋ ์์ฃผ ์ฌ์ฉ๋๋ ์ปฌ๋ผ์ ์์์ ์์ ๋๋ ๊ฒ์ด ์ข์
 - ํ์ด๋ธ์ ๋ง๋ค ์ ์๋ ์ธ๋ฑ์ค ์์ ์ ํ์ ์์ผ๋ ๋๋ฌด ๋ง์ด ๋ง๋ค๋ฉด ๋ถํ๊ฐ ๋ฐ์ํจ  
      
 - ์ธ๋ฑ์ค ์ญ์   
   DROP INDEX ์ธ๋ฑ์ค๋ช;  
      
### ๐ฉ ์ํ์ค  
 - ์ํ์ค ์์ฑ  
   CREATE SEQUENCE ์ํ์ค๋ช  
   INCREMENT BY ์ฆ๊ฐ์ซ์ : 0์ด ์๋ ์ ์, ์์๋ฉด ์ฆ๊ฐ, ์์๋ฉด ๊ฐ์, ๋ํดํธ 1   
   START WITH ์์์ซ์ : ๋ํดํธ ๊ฐ์ ์ฆ๊ฐ์ผ ๋๋ MINVALUE, ๊ฐ์์ผ ๊ฒฝ์ฐ MAXVALUE    
   NOMINVALUE | MINVALUE ์ต์๊ฐ : ์์์ซ์๋ณด๋ค ์๊ฑฐ๋ ๊ฐ์์ผ ํ๊ณ  MAXVALUE๋ณด๋ค ์์์ผ ํจ    
   NOMAXVALUE | MAXVALUE ์ต๋๊ฐ : ์์์ซ์๋ณด๋ค ํฌ๊ฑฐ๋ ๊ฐ์์ผ ํ๊ณ  MINVALUE๋ณด๋ค ์ปค์ผ ํจ    
   NOCYCLE | CYCLE : CYCLE: ์ฆ๊ฐ๋ ํด๋๊ฐ์ ๋๋ฌํ๋ฉด ๋ค์ ์ต์๊ฐ๋ถํฐ ์์, ๊ฐ์๋ ์ต์๊ฐ์ ๋๋ฌํ๋ฉด ๋ค์ ์ต๋ ๊ฐ์์ ์์, NOCYCLE : ๋ํดํธ ๊ฐ์ผ๋ก ์ต๋๋ ์ต์๊ฐ์ ๋๋ฌํ๋ฉด ์์ฑ ์ค์ง       
   NOCACHE | CACHE; : NOCACHE : ๋ํดํธ๋ก ๋ฉ๋ชจ๋ฆฌ์ ์ํ์ค ๊ฐ์ ๋ฏธ๋ฆฌ ํ ๋นํด ๋์ง ์์ผ๋ฉฐ ๋ํดํธ ๊ฐ์ 20, CACHE : ๋ฉ๋ชจ๋ฆฌ์ ์ํ์ค ๊ฐ์ ๋ฏธ๋ฆฌ ํ ๋นํด ๋์   
      
   INSERT INTO ํ์ด๋ธ๋ช(์ปฌ๋ผ๋ช) VALUES (์ํ์ค๋ช.NEXTVAL); : INSERT๋ SELECT ํ  ๋๋ง๋ค ์ํ์ค ์ฆ๊ฐ์ซ์๋งํผ ์ฆ๊ฐ  
      
 - ์ํ์ค ์ญ์   
   DROP SEQUENCE ์ํ์ค๋ช;  
      
### ๐ฉ ํํฐ์ ํ์ด๋ธ    
 - ํ์ด๋ธ์ ์์ฑํ  ๋ ํํฐ์์ผ๋ก ํ์ด๋ธ์ ๋ง๋ค ์ ์๋ค.  
 - ํ์ด๋ธ์ ์๋ ํน์  ์ปฌ๋ผ ๊ฐ์ ๊ธฐ์ค์ผ๋ก ๋ฐ์ดํฐ๋ฅผ ๋ถํ ํด ์ ์ฅํด ๋๋ ๊ฒ.  
 - ๋ผ๋ฆฌ์ ์ผ๋ก ํ์ด๋ธ์ 1๊ฐ์ง๋ง, ๋ฌผ๋ฆฌ์ ์ผ๋ก๋ ํํฐ์๋ณ๋ก ๋ฐ์ดํฐ๊ฐ ์ ์ฅ๋๋ค.  
 - ๋์ฉ๋ ํ์ด๋ธ์ ๊ฒฝ์ฐ ๋ฐ์ดํฐ ์กฐํ ์ ํจ์จ์ฑ๊ณผ ์ฑ๋ฅ์ ๋์ด๊ธฐ ์ํ ๊ฒ.  
      
   ex) CREATE TABLE ํ์ด๋ธ๋ช (    
         ์ปฌ๋ผ1 NUMBER(6,0) NOT NULL,  
         ์ปฌ๋ผ2 VARCHAR2(10),  
         ์ปฌ๋ผ3 DATE DEFAULT SYSDATE NOT NULL,  
         ์ปฌ๋ผ4 VARCHAR2(6 ),  
         ...  
       )  
       PARTITION BY RANGE(์ปฌ๋ผ4) (    
         ...  
         PARTITION SALES_Q1_2021 VALUES LESS THAN ('202104') TABLESPACE MYTS, --1๋ถ๊ธฐ   
         PARTITION SALES_Q2_2021 VALUES LESS THAN ('202107') TABLESPACE MYTS, --2๋ถ๊ธฐ     
         PARTITION SALES_Q3_2021 VALUES LESS THAN ('202110') TABLESPACE MYTS, --3๋ถ๊ธฐ   
         PARTITION SALES_Q4_2021 VALUES LESS THAN ('202201') TABLESPACE MYTS, --4๋ถ๊ธฐ   
         ...  
       ); 
</details>  
<details>
  <summary>๐ SQL ๋ฌธ์ฅ </summary>
 
## ๐ SQL ๋ฌธ์ฅ    
### ๐ฉ SELECT๋ฌธ  
 - ํ์ด๋ธ์ด๋ ๋ทฐ์ ์๋ ๋ฐ์ดํฐ๋ฅผ ์กฐํํ  ๋ ์ฌ์ฉ  
 - SELECT * OR ์ปฌ๋ผ๋ช  
   FROM ํ์ด๋ธ๋ช OR ๋ทฐ๋ช  
   WHERE ์กฐ๊ฑด    
   ORDER BY ์ปฌ๋ผ๋ช; 

### ๐ฉ INSERT๋ฌธ  
 - ์ ๊ท๋ก ๋ฐ์ดํฐ ์๋ ฅ์ ์ฌ์ฉ  
 - INSERT INTO ํ์ด๋ธ๋ช (์ปฌ๋ผ1, ์ปฌ๋ผ2, ...)  
   VALUES (๊ฐ1, ๊ฐ2, ...)  
 - ์ฌ์ ํ์ด๋ธ์์ ์๊ธ์ด 5000 ์ด์์ธ ์ฌ์์ ์ฌ์๋ฒํธ์ ์ฌ์๋ช์ ์กฐํํ ๊ฒฐ๊ณผ๋ฅผ ex3 ํ์ด๋ธ์ ๋ฃ๊ธฐ  
   INSERT INTO ex3 (emp_id, emp_name)  
   SELECT employee_id, employee_name  
   FROM employees  
   WHERE salary > 5000;  
      
### ๐ฉ UPDATE๋ฌธ  
 - UPDATE ํ์ด๋ธ๋ช  
   SET ์ปฌ๋ผ1 = ๋ณ๊ฒฝ๊ฐ1,  
       ์ปฌ๋ผ2 = ๋ณ๊ฒฝ๊ฐ2,  
       ...  
   WHERE ์กฐ๊ฑด;  
 
### ๐ฉ MERGE๋ฌธ  
 -  MERGE INTO ํ์ด๋ธ๋ช  
    USING (update๋ insert๋  ๋ฐ์ดํฐ ์์ฒ) ON (update๋  ์กฐ๊ฑด)  
    WHEN MATCHED THEN  
      SET ์ปฌ๋ผ1 =  ๊ฐ1, ์ปฌ๋ผ2 = ๊ฐ2, ...  
    WHERE UPDATE ์กฐ๊ฑด  
      DELETE WHERE update_delete ์กฐ๊ฑด  
    WHEN NOT MATCHED THEN  
      INSERT(์ปฌ๋ผ1, ์ปฌ๋ผ2, ...) VALUES (๊ฐ1, ๊ฐ2, ...)  
      WHERE insert ์กฐ๊ฑด;  
      
 - ex) MERGE INTO ex3 a  
       USING (SELECT employee_id, salary, manager_id   
              FROM employees   
              WHERE manager_id = 146) b   
       ON (a.employee_id = b.employee_id)  
       WHEN MATCHED THEN  
         UPDATE SET a.bonus_amt = b.bonus_amt + a.salary * 0.01  
         --DELETE WHERE (b.employee_id = 161) ์ถ๊ฐํด์ฃผ๋ฉด 161๋ฒ ์ฌ์์ ์ญ์ ๋จ  
       WHEN NOT MATCHED THEN  
         INSERT (a.employee_id, b.bonus_amt) VALUES (b.employee_id, b.salary*0.01)  
         WHERE (b.salary < 8000);  
      
### ๐ฉ DELETE๋ฌธ  
 - ํ์ด๋ธ์ ์๋ ๋ฐ์ดํฐ๋ฅผ ์ญ์ ํ  ๋ ์ฌ์ฉ, COMMIT, ROLLBACK ๊ฐ๋ฅ. TRUNCATE๋ฌธ์ ๋ณต๊ท ๋ถ๊ฐ, WHERE ์กฐ๊ฑด ๋ถ์ผ ์ ์์  
 - DELETE ex3;  
 - TRUNCATE TABLE ex3;  
                                 
### ๐ฉ ์์ฌ์ปฌ๋ผ  
 - ํ์ด๋ธ์ ์ปฌ๋ผ์ฒ๋ผ ๋์ํ์ง๋ง ์ค์ ๋ก ํ์ด๋ธ์ ์ ์ฅ๋์ง๋ ์๋ ์ปฌ๋ผ  
 - SELECT๋ฌธ์์๋ ์์ฌ์ปฌ๋ผ ์ฌ์ฉ ๊ฐ๋ฅ  
 - CONNECT_BY_ISCYCLE, CONNECT_BY_ISLEAF,LEVEL  
 - NEXTVAL, CURRVAL  
 - ROWNUM, ROWID  
 - SELECT ROWNUM, employee_id  
   FROM employees  
   WHERE ROWNUM < 5;  
      
### ๐ฉ ์ฐ์ฐ์  
 - ์์ ์ฐ์ฐ์ : +,-,*,/  
 - ๋ฌธ์ ์ฐ์ฐ์ : ||  
 - ๋ผ๋ฆฌ ์ฐ์ฐ์ : >,<,>=,<=,=,<>,!=,^=       
 - ์งํฉ ์ฐ์ฐ์ : UNION, UNION ALL, INTERSECT, MINUS  
 - ๊ณ์ธตํ ์ฟผ๋ฆฌ ์ฐ์ฐ์ : PRIOR, CONNECT_BY_ROOT      
      
### ๐ฉ ํํ์  
 - ํ ๊ฐ ์ด์์ ๊ฐ๊ณผ ์ฐ์ฐ์, SQL ํจ์ ๋ฑ์ด ๊ฒฐํฉ๋ ์  
 - CASE WHEN ์กฐ๊ฑด1 THEN ๊ฐ1  
        WHEN ์กฐ๊ฑด2 THEN ๊ฐ2  
        ...  
        ELSE ๊ธฐํ ๊ฐ  
   END  
 - ex) SELECT employee_id, salary,  
              CASE WHEN salary <= 5000 THEN 'C๋ฑ๊ธ'  
                   WHEN salary > 5000 AND salary <= 15000 THEN 'B๋ฑ๊ธ' ELSE 'A๋ฑ๊ธ' END AS salary_grade  
       FROM employees;  

### ๐ฉ ์กฐ๊ฑด์  
 - ๋น๊ต ์กฐ๊ฑด์(ANY, ALL, SOME)  
   SELECT employee_id, salary  
   FROM employees  
   WHERE salary = ANY (2000, 3000, 4000) --ํด๋น ๊ฐ๋ค์ค ํ๋๋ง ๋ง์กฑํด๋.    
   ORDER BY employee_id;  
                                                        
   SLECT employee_id, salary  
   FROM employees  
   WHERE salary = ALL(2000, 3000, 4000) --๋์์ ๋ชจ๋  ์กฐ๊ฑด์ ๋ง์กฑํ๋ฉด.  
   ORDER BY employee_id;  
                                                        
   SELECT employee_id, salary  
   FROM employees  
   WHERE salary = SOME (2000, 3000, 4000) --ANY์ ๋์ผํ๊ฒ ์ฌ์ฉ๋จ.  
   ORDER BY employee_id;  
 
 - ๋ผ๋ฆฌ ์กฐ๊ฑด์(AND, OR, NOT)  
   SELECT employee_id, salary  
   FROM employees  
   WHERE NOT (salary >= 2500) --๊ฑฐ์ง์ผ ๋ true ๋ฐํ  
   ORDER BY employee_id;    
  
 - NULL ์กฐ๊ฑด์  
   ๋ฑํธ ์ฐ์ฐ์ ์ฌ์ฉํ์ง ๋ง๊ณ  salary IS NULL ํน์ salary IS NOT NULL๋ก ๋น๊ตํด์ผ ํจ  
 
 - BETWEEN AND ์กฐ๊ฑด์  
   SELECT employee_id, salary  
   FROM employees  
   WHERE salary BETWEEN 2000 AND 2500 -- ๊ธ์ฌ๊ฐ 2000 ~ 2500 ์ฌ์ด    
   ORDER BY employee_id;  
  
 - IN ์กฐ๊ฑด์  
   SELECT employee_id, salary  
   FROM employees  
   WHERE salary IN (2000, 3000, 4000) -- ๊ธ์ฌ๊ฐ 2000, 3000, 4000์ ํฌํจ๋๋ ์ฌ์    
   ORDER BY employee_id;  
  
   SELECT employee_id, salary  
   FROM employees  
   WHERE salary NOT IN (2000, 3000, 4000) -- ๊ธ์ฌ๊ฐ 2000, 3000, 4000์ ํฌํจ๋์ง ์๋ ์ฌ์ 
   ORDER BY employee_id;  
  
 - EXISTS ์กฐ๊ฑด์  
   SELECT department_id, department_name  
   FROM departments a
   WHERE EXISTS ( SELECT *  
                  FROM employees b  
                  WHERE a.department_id = b.department_id -- IN๊ณผ ๋น์ทํ์ง๋ง ํํ ์กฐ๊ฑด์ ๋ก ๊ฐ์ ๋ฆฌ์คํธ๊ฐ ์๋ ์๋ธ์ฟผ๋ฆฌ๋ง ์ฌ ์ ์์. ์๋ธ์ฟผ๋ฆฌ ๋ด์ ์กฐ์ธ ์กฐ๊ฑด์ด ์์ด์ผ ํจ.    
                  AND b.salary> 3000)  
   ORDER BY a.department_name; 
  
 - LIKE ์กฐ๊ฑด์  
   SELECT emp_name  
   FROM employees  
   WHERE emp_name LIKE 'A%' -- A๋ก ์์ํ๋ ๋๋จธ์ง๋ ์ด๋ค ๊ธ์๊ฐ ์๋ ์๊ด์์ด ๋ชจ๋ ์กฐํ, ๋์๋ฌธ์ ๊ตฌ๋ถ, %๊ฐ ์๋ _์ ๋๋จธ์ง ๊ธ์ ์ ์ฒด๊ฐ ์๋ ํ ๊ธ์๋ง ๋น๊ต    
   ORDER BY emp_name;  
</details>
<details>
  <summary>๐ SQL ํจ์</summary> 
  
### ๐ฉ ์ซ์ ํจ์  
 - ABS(n) : ์ ๋๊ฐ ๋ฐํ  
   SELECT ABS(10), ABS(-10), ABS(-10.123) --๊ฒฐ๊ณผ 10 10 10.123   
   FROM DUAL;  
 - CEIL(n) : ๋งค๊ฐ๋ณ์ n๊ณผ ๊ฐ๊ฑฐ๋ ๊ฐ์ฅ ํฐ ์ ์ ๋ฐํ    
   SELECT CEIL(10.123), CEIL(10.541), CEIL(11.001) --๊ฒฐ๊ณผ 11 11 12     
   FROM DUAL;  
 - FLOOR(n) : ๋งค๊ฐ๋ณ์ n๋ณด๋ค ์๊ฑฐ๋ ๊ฐ์ฅ ํฐ ์ ์ ๋ฐํ  
   SELECT FLOOR(10.123), FLOOR(10.541), FLOOR(11.001) --๊ฒฐ๊ณผ 10 10 11    
   FROM DUAL;  
 - ROUND(n,i) : ๋งค๊ฐ๋ณ์ n์ ์์์  ๊ธฐ์ค (i_1)๋ฒ ์งธ์์ ๋ฐ์ฌ๋ฆผํ ๊ฒฐ๊ณผ ๋ฐํ, i๋ ์๋ต ๊ฐ๋ฅ, ๋ํดํธ ๊ฐ์ 0  
   SELECT ROUND(10.154), ROUND(10.541), ROUND(11.001) --๊ฒฐ๊ณผ 10 11 11    
   FROM DUAL;  
    
   SELECT ROUND(10.541, 1), ROUNG(10.154, 2), ROUND(10.154, 3) --๊ฒฐ๊ณผ 10.2 10.15 10.154    
   FROM DUAL;  
    
   SELECT ROUNG(0, 3), ROUND(115.155, -1), ROUND(115.155, -2) --๊ฒฐ๊ณผ 0 120 100    
   FROM DUAL;  
  
 - TRUNC : ๋ฐ์ฌ๋ฆผ ํ์ง ์๊ณ  n1์ ์์์  ๊ธฐ์ค n2 ์๋ฆฌ์์ ๋ฌด์กฐ๊ฑด ์๋ผ๋ธ ๊ฒฐ๊ณผ ๋ฐํ, n2 ์๋ต ๊ฐ๋ฅ, ๋ํดํธ ๊ฐ 0  
   SELECT TRUNC(115.155), TRUNC(115.155, 1), TRUNC(115.155, 2), TRUNC(115.155, -2) -- ๊ฒฐ๊ณผ 115 115.1 115.15 100    
   FROM DUAL;  
    
 - POWER(n2, n1) : n2๋ฅผ n1 ์ ๊ณฑํ ๊ฒฐ๊ณผ ๋ฐํ, n2๊ฐ ์์์ผ ๋ n1์ ์ ์๋ง ์ฌ ์ ์์  
   SELECT POWER(3,2), POWER(3,3), POWER(3,3.0001) -- ๊ฒฐ๊ณผ 9 27 27.0029664    
   FROM DUAL;  
    
 - SORT : n์ ์ ๊ณฑ๊ทผ ๋ฐํ  
   SELECT SORT(2), SORT(5) --๊ฒฐ๊ณผ 1.141421356   2.23606798     
   FROM DUAL;  
    
 - MOD(n2, n1) : n2๋ฅผ n1์ผ๋ก ๋๋ ๋๋จธ์ง ๊ฐ ๋ฐํ  
   SELECT MOD(19,4), MOD(19.123, 4.2) --๊ฒฐ๊ณผ 3  2.323    
   FROM DUAL;  
  
 - EXP(n) : ์ง์ ํจ์๋ก e(e=2.71828183...)์ n์ ๊ณฑ ๊ฐ์ ๋ฐํ  
   LN(n) : ์์ฐ ๋ก๊ทธ ํจ์๋ก ๋ฐ์๊ฐ e์ธ ๋ก๊ทธ ํจ์  
   LOG(n2, n1) : n2๋ฅผ ๋ฐ์๋ก ํ๋ n1์ ๋ก๊ทธ ๊ฐ์ ๋ฐํ  
    
   SELECT EXP(2), LN(2.713), LOG(10, 100) --๊ฒฐ๊ณผ 7.3890561     0.998055034     2    
   FROM DUAL;  
  
### ๐ฉ ๋ฌธ์ ํจ์  
 - INITCAP(char) :  ๋งค๊ฐ๋ณ์๋ก ๋ค์ด์ค๋ char์ ์ฒซ ๋ฌธ์๋ ๋๋ฌธ์๋ก ๋๋จธ์ง๋ ์๋ฌธ์๋ก ๋ฐํ, ์ฒซ ๋ฌธ์ ์ธ์ ๊ธฐ์ค์ ๊ณต๋ฐฑ๊ณผ ์ํ๋ฒณ(์ซ์ ํฌํจ)์ ์ ์ธํ ๋ฌธ์    
   SELECT INITCAP('never say goodbye') --๊ฒฐ๊ณผ Never Say Goodbye    
   FROM DUAL;  
  
 - LOWER : ๋งค๊ฐ๋ณ์๋ก ๋ค์ด์ค๋ ๋ฌธ์๋ฅผ ๋ชจ๋ ์๋ฌธ์๋ก.  
   UPPER : ๋ชจ๋ ๋๋ฌธ์๋ก ๋ณํํด ๋ฐํ.  
   SELECT LOWER('NEVER SAY GOODBYE'), UPPER('never say goodbye') --๊ฒฐ๊ณผ never say goodbye    NEVER SAY GOODBYE    
   FROM DUAL;  
    
 - CONCAT(char1, char2) : ๋งค๊ฐ๋ณ์๋ก ๋ค์ด์ค๋ ๋ ๋ฌธ์๋ฅผ ๋ถ์ฌ ๋ฐํ  
   SELECT CONCAT('I Have', 'A Dream) --๊ฒฐ๊ณผ I Have A Dream    
   FROM DUAL;  
   
 - SUBSTR(char, pos, len) : ์๋ผ์ฌ ๋์ฌ ๋ฌธ์์ด์ธ char์ pos๋ฒ์งธ ๋ฌธ์๋ถํฐ len๊ธธ์ด๋งํผ ์๋ผ๋ธ ๊ฒฐ๊ณผ ๋ฐํ  
   SELECT SUBSTR('ABCDEFG', 1, 4), SUBSTR('ABCDEFG', -1, 4) --๊ฒฐ๊ณผ ABCD    G  
   FROM DUAL;  
    
 - LTRIM(char, set) : ๋งค๊ฐ๋ณ์๋ก ๋ค์ด์จ char ๋ฌธ์์ด์์ set์ผ๋ก ์ง์ ๋ ๋ฌธ์์ด์ ์ผ์ชฝ ๋์์ ์ ๊ฑฐํ ํ ๋๋จธ์ง ๋ฌธ์์ด ๋ฐํ, ๋ฌธ์์ด ์ค๊ฐ์ ์๋ค๋ฉด ๋ฌธ์์ด ์ ์ฒด ๋ฐํ    
   RTRIM(char, set) : ์ค๋ฅธ์ชฝ ๋์์ ์ ๊ฑฐํ ํ ๋๋จธ์ง ๋ฌธ์์ด ๋ฐํ  
   SELECT LTRIM('ABCDEFGABC', 'ABC'),  --๊ฒฐ๊ณผ DEFGABC     ๋๋ค๋ผ     ABCDEFG     ๊ฐ๋๋ค  
          LTRIM('๊ฐ๋๋ค๋ผ', '๊ฐ'),  
          RTRIM('ABCDEFGABC', 'ABC'),  
          RTRIM('๊ฐ๋๋ค๋ผ', '๋ผ')  
   FROM DUAL;  
    
 - LPAD(expr1, n, expr2) : ๋งค๊ฐ๋ณ์๋ก ๋ค์ด์จ expr2 ๋ฌธ์์ด์ n์๋ฆฌ๋งํผ ์ผ์ชฝ๋ถํฐ ์ฑ์ expr1์ ๋ฐํ, ๋งค๊ฐ๋ณ์ n์ expr1๊ณผ expr2๊ฐ ํฉ์ณ์ ธ ๋ฐํ๋๋ ์ด ์๋ฆฟ์  
   RPAD(expr1, n, expr2) : ์ค๋ฅธ์ชฝ๋ถํฐ ์ฑ์  
   SELECT LPAD(phone_num, 12, '(02)') --๊ฒฐ๊ณผ (02)111-1111     (02)111-2222      ...  
   FROM EX4_1;  
    
 - REPLACE(char, search_str, replace_str) : char๋ฌธ์์ด์์ search_str๋ฌธ์์ด์ ์ฐพ์ replace_str๋ฌธ์์ด๋ก ๋์ฒดํ ๊ฒฐ๊ณผ ๋ฐํ  
   SELECT REPLACE('๋๋ ๋๋ฅผ ๋ชจ๋ฅด๋๋ฐ ๋๋ ๋๋ฅผ ์๊ฒ ๋๊ฐ', '๋๋', '๋๋ฅผ') --๊ฒฐ๊ณผ ๋๋ ๋๋ฅผ ๋ชจ๋ฅด๋๋ฐ ๋๋ ๋๋ฅผ ์๊ฒ ๋๊ฐ    
   FROM DUAL;  
    
   SELECT REPLACE('ABC DEF', '', '') --๊ฒฐ๊ณผ ABCDEF    
   FROM DUAL;  
  
 - TRANSLATE(expr, FROM_str, to_str) : ๋ฌธ์์ด ์์ฒด๊ฐ ์๋ ๋ฌธ์ ํ ๊ธ์์ฉ ๋งคํํด ๋ฐ๊พผ ๊ฒฐ๊ณผ ๋ฐํ  
   SELECT TRANSLATE('๋๋ ๋๋ฅผ ๋ชจ๋ฅด๋๋ฐ ๋๋ ๋๋ฅผ ์๊ฒ ๋๊ฐ', '๋๋', '๋๋ฅผ') --๊ฒฐ๊ณผ ๋๋ฅผ ๋๋ฅผ ๋ชจ๋ฅด๋ฅผ๋ฐ ๋๋ฅผ๋๋ฅผ ์๊ฒ ๋ฅผ๊ฐ  
   FROM DUAL;  
  
 - INSTR(str, substr, pos, occur) :  str๋ฌธ์์ด์์ substr๊ณผ ์ผ์นํ๋ ์์น ๋ฐํ, pos๋ ์์์์น๋ก ๋ํดํธ 1, occur์ ๋ช ๋ฒ์งธ ์ผ์นํ๋์ง ๋ช์ ๋ํดํธ 1  
   SELECT INSTR('๋ด๊ฐ ๋ง์ฝ ์ธ๋ก์ธ ๋๋ฉด, ๋ด๊ฐ ๋ง์ฝ ๊ดด๋ก์ธ ๋๋ฉด', '๋ง์ฝ') --๊ฒฐ๊ณผ 4  
          INSTR('๋ด๊ฐ ๋ง์ฝ ์ธ๋ก์ธ ๋๋ฉด, ๋ด๊ฐ ๋ง์ฝ ๊ดด๋ก์ธ ๋๋ฉด', '๋ง์ฝ', 5) --๊ฒฐ๊ณผ 18  
   FROM DUAL;
  
 - LENGTH(chr) : ๋งค๊ฐ๋ณ์๋ก ๋ค์ด์จ ๋ฌธ์์ด์ ๊ฐ์ ๋ฐํ  
   SELECT LENGTH('๋ํ๋ฏผ๊ตญ') --๊ฒฐ๊ณผ 4  
   FROM DUAL;  
  
### ๐ฉ ๋ ์ง ํจ์  
 - DATEํจ์๋ TIMESTAMP ํจ์์ ๊ฐ์ ๋ ์งํ์ ๋์์ผ๋ก ์ฐ์ฐ์ ์ํํด ๊ฒฐ๊ณผ๋ฅผ ๋ฐํ
1. SYSDATE : ํ์ฌ ์ผ์์ ์๊ฐ์ DATEํ์ผ๋ก ๋ฐํ
    
    SYSTIMESTAMP : ํ์ฌ ์ผ์์ ์๊ฐ์ TIMESTAMPํ์ผ๋ก ๋ฐํ
    
    ```sql
    SELECT SYSDATE, SYSTIMESTAMP
    FROM DUAL;
    -- 2021-07-26 17:06:25
    -- 2021-07-26 17:06:25.99800000000 +09:00
    ```
    
2. ADD_MONTHS(date, integer) : ๋งค๊ฐ๋ณ์๋ก ๋ค์ด์จ ๋ ์ง์ integer๋งํผ์ ์์ ๋ํ ๋ ์ง ๋ฐํ
    
    ```sql
    SELECT ADD_MONTHS(SYSDATE,1), ADD_MONTHS(SYSDATE, -1)
    FROM DUAL;
    -- 2021-08-26 17:06:25
    -- 2021-06-26 17:06:25
    ```
    
3. MONTHS_BETWEEN(date1, date2) : ๋ ๋ ์ง ์ฌ์ด์ ๊ฐ์ ์ ๋ฐํ, date2๊ฐ date1๋ณด๋ค ๋น ๋ฅธ ๋ ์ง๊ฐ ์ด
    
    ```sql
    SELECT MONTHS_BETWEEN(SYSDATE, ADD_MONTHS(SYSDATE, 1)) mon1,
    			 MONTHS_BETWEEN(ADD_MONTHS(SYSDATE, 1), SYSDATE) mon2
    FROM DUAL;
    -- -1      1
    
    --20๋ ๊ณ ๊ฐ์ ๊ตฌํ๊ธฐ
    SELECT COUNT(customer_id)
    FROM customers
    WHERE FLOOR(MONTHS_BETWEEN(SYSDATE, date_of_birth) / 12) BETWEEN 20 AND 29;
    ```
    
4. LAST_DAY(date) : date ๋ ์ง๋ฅผ ๊ธฐ์ค์ผ๋ก ํด๋น ์์ ๋ง์ง๋ง ์ผ์๋ฅผ ๋ฐํ
    
    ```sql
    SELECT LAST_DAY(SYSDATE)
    FROM DUAL;
    -- 2021-07-31 17:06:25
    ```
    
5. ROUND(date, format) : ๋ฐ์ฌ๋ฆผํ ๋ ์ง ๋ฐํ
    
    TRUNC(date, format) : ์๋ผ๋ธ ๋ ์ง ๋ฐํ
    
    ```sql
    SELECT SYSDATE, ROUND(SYSDATE, 'month'), TRUNC(SYSDATE, 'month')
    FROM DUAL;
    -- 2021-07-26 17:06:25      2021-08-01 00:00:00      2021-07-01 00:00:00
    ```
    
6. NEXT_DAY(date, char) : date๋ฅผ char์ ๋ช์ํ ๋ ์ง๋ก ๋ค์ ์ฃผ ์ฃผ์ค ์ผ์๋ฅผ ๋ฐํ
    
    ```sql
    SELECT NEXT_DAY(SYSDATE, '๊ธ์์ผ')
    FROM DUAL;
    -- 2021-07-31 17:06:25
    ``` 
  
### ๐ฉ ๋ณํ ํจ์ 
  - ์๋ก ๋ค๋ฅธ ์ ํ์ ๋ฐ์ดํฐ ํ์์ผ๋ก ๋ณํํด ๊ฒฐ๊ณผ๋ฅผ ๋ฐํ
1. TO_CHAR(์ซ์ ํน์ ๋ ์ง, format) : ์ซ์๋ ๋ ์ง๋ฅผ ๋ฌธ์๋ก ๋ณํ 
    
     
    
    ```sql
    SELECT TO_CHAR(123456789, '999,999,999')
    FROM DUAL;
    -- 123,456,789
    
    SELECT TO_CHAR(SYSDATE, 'YYYY-MM-DD')
    FROM DUAL;
    -- 2021-07-26
    ```
    

2. TO_NUMBER(expr, format) : ๋ฌธ์๋ใ ๋ค๋ฅธ ์ ํ์ ์ซ์๋ฅผ NUMBERํ์ผ๋ก ๋ณํ

    ```sql
    SELECT TO_NUMBER('123456')
    FROM DUAL;
    -- 123456
    ```

3. TO_DATE(char, format) : ๋ฌธ์๋ฅผ DATEํ์ผ๋ก ๋ณํ
    
    TO_TIMESTAMP(char, format) : ๋ฌธ์๋ฅผ TIMESTAMPํ์ผ๋ก ๋ณํ
    
    ```sql
    SELECT TO_DATE('20210726', 'YYYY-MM-DD')
    FROM DUAL;
    -- 2021/07/26 00:00:00
    
    SELECT TO_DATE('2021072617:36:50', 'YYYY-MM-DD HH24:MI:SS')
    FROM DUAL;
    -- 2021/07/26 17:36:50
    ``` 
  
### ๐ฉ NULL ๊ด๋ จ ํจ์ 
1. NVL(expr1, expr2) : expr1์ด NULL์ผ ๋ expr2 ๋ฐํ
    
    ```sql
    SELECT NVL(manager_id, employee_id)
    FROM employees
    WHERE manager_id IS NULL;
    -- 100
    ```
    
2. NVL2(expr1, expr2, expr3) : expr1์ด NULL์ด ์๋๋ฉด expr2๋ฅผ NULL์ด๋ฉด expr3์ ๋ฐํ 
    
    ```sql
    SELECT employee_id,
    			 NVL2(commission_pct, salary + (salary * commission_pct), salary)AS salary2
    FROM employees;
    -- EMPLOYEE_ID      SALARY2
    --         198         2600
    --         199         2600
    --         200         4400
    -- ...
    -- 107๊ฐ์ ํ์ด ์ ํ๋จ.
    ```
    
3. COALESCE(expr1, expr2, ...) : ๋งค๊ฐ๋ณ์๋ก ๋ค์ด์ค๋ ํํ์์์ NULL์ด ์๋ ์ฒซ ๋ฒ์งธ ํํ์์ ๋ฐํ. NULL๊ณผ ์์ ์ฐ์ฐ์๋ฅผ ์ฌ์ฉํด NULL๊ณผ ์ฐ์ฐ์ ํ๋ฉด ์๋๊ฐ์ด ๋ฌด์์ด๋  ๋ฌด์กฐ๊ฑด NULL์ด ๋ฐํ๋จ.
    
    ```sql
    SELECT employee_id, salary, commission_pct,
    			 COALESCE(salary * commission_pct, salary)AS salary2
    FROM employees;
    -- EMPLOYEE_ID       SALARY       COMMISSION_PCT       SALARY2
    --         143         2600                               2600
    --         144         2500                               2500
    --         145        14000                  0.4          5600
    --         146        13500                  0.3          4050
    -- ...
    -- 107๊ฐ์ ํ์ด ์ ํ๋จ.
    ```
    
4. LNNVL(์กฐ๊ฑด์) : ๋งค๊ฐ๋ณ์๋ก ๋ค์ด์ค๋ ์กฐ๊ฑด์์ ๊ฒฐ๊ณผ๊ฐ FALSE๋ UNKNOWN์ด๋ฉด TRUE, TRUE์ด๋ฉด FALSE ๋ฐํ
    
    ```sql
    SELECT COUNT(*)
    FROM employees
    WHERE NVL(commission_pct, 0) < 0.2;
    -- 83
    
    SELECT COUNT(*)
    FROM employees
    WHERE LNNVL(commission_pct >= 0.2);
    -- 83
    ```
    
5. NULLIF(expr1, expr2) : expr1๊ณผ expr2๋ฅผ ๋น๊ตํด ๊ฐ์ผ๋ฉด NULL, ๊ฐ์ง ์์ผ๋ฉด expr1 ๋ฐํ
    
    ```sql
    SELECT employee_id,
    			 TO_CHAR(start_date, 'YYYY') start_year,
    			 TO_CHAR(end_date, 'YYYY') end_year,
    			 NULL_IF(TO_CHAR(end_date, 'YYYY'), TO_CHAR(start_date, 'YYYY')) nullif_year
    FROM job_history;
    -- EMPLOYEE_ID    START_YEAR     END_YEAR NULLIF_YEAR
    --     1022001          2006                     2006
    --     1011997          2001                     2001
    --     1222007          2007                     
    --     2001995          2001                     2001
    -- ...
    -- 10๊ฐ์ ํ์ด ์ ํ๋จ.
    -- start_date์ end_date์ ์ฐ๋๋ง ์ถ์ถํด ๋ ์ฐ๋๊ฐ ๊ฐ์ผ๋ฉด NULL, ์๋๋ฉด ์ข๋ฃ๋๋ ์ถ๋ ฅ
    ``` 
  
### ๐ฉ ๊ธฐํ ํจ์ 
1. GREATEST(expr1, expr2, ...) : ๋งค๊ฐ๋ณ์๋ก ๋ค์ด์ค๋ ํํ์์์ ๊ฐ์ฅ ํฐ ๊ฐ์ ๋ฐํ
    
    LEAST(expr1, expr2, ...) : ๊ฐ์ฅ ์์ ๊ฐ์ ๋ฐํ
    
    ```sql
    SELECT GREATEST(1, 2, 3, 2),
    			 LEAST(1, 2, 3, 2)
    FROM DUAL;
    -- 3      1
    
    SELECT GREATEST('์ด์์ ', '๊ฐ๊ฐ์ฐฌ', '์ธ์ข๋์'),
    		   LEAST('์ด์์ ', '๊ฐ๊ฐ์ฐฌ', '์ธ์ข๋์')
    FROM DUAL;
    -- ์ด์์       ๊ฐ๊ฐ์ฐฌ
    ```
    
2. DECODE(expr, search1, result1, search2, result2, ..., default) : expr๊ณผ search1์ ๋น๊ตํด ๋ ๊ฐ์ด ๊ฐ์ผ๋ฉด  result1์, ๊ฐ์ง ์์ผ๋ฉด ๋ค์ search2์ ๋น๊ตํด ๊ฐ์ด ๊ฐ์ผ๋ฉด result2๋ฅผ ๋ฐํํ๊ณ  ๊ณ์ ํ ๋ค ์ต์ข์ ์ผ๋ก ๊ฐ์ ๊ฐ์ด ์์ผ๋ฉด default ๊ฐ์ ๋ฐํ. DECODE ๋ณด๋ค๋ CASE ํํ์์ ์ฌ์ฉํ๋ ๊ฒ์ด ์ฝ๋๊ฐ ๊น๋ํด์ง.
    
    ```sql
    SELECT prod_id
    			 DECODE(channel_id, 3, 'Direct',
    													9, 'Direct',
    												  5, 'Indirect',
    													4, 'Indirect',
    														 'Others') decodes
    FROM sales
    WHERE ROWNUM < 10;
    -- PROD_ID   DECODES
    --      18   Others
    --      18   Indirect
    --      18   Indirect
    --      18   Others
    -- 9๊ฐ์ ํ์ด ์ ํ๋จ.
    ``` 
 </details> 
  
 ## ๐ Mybatis์์ CDATA ์ฌ์ฉํ๊ธฐ!!!   
    
    <if test='depCd != null and depCd != "" '>
        AND depCd <![CDATA[ >= ]]> #{depCd }
    </if>
    
    - ์ฟผ๋ฆฌ๋ฌธ์ ๋ฌธ์์ด ๋น๊ต ์ฐ์ฐ์๋ ๋ถ๋ฑํธ ์ฒ๋ฆฌ๋ฅผ ํ  ๋ <์ ๊ฐ์ ๊ธฐํธ๊ฐ ๊ดํธ์ธ์ง ๋น๊ต์ฐ์ฐ์์ธ์ง ํ์ธ์ด ์๋๊ณ  ํน์๋ฌธ์ ์ฌ์ฉ์๋ 
      ์ ํ์ด ์์ด์ ์ฌ์ฉํจ. CDATA ํ๊ทธ ์์์๋ ์ ๋ถ ๋ฌธ์์ด๋ก ์นํ์์ผ๋ฒ๋ฆผ. 
                                      
 ## ๐ statementType="CALLABLE" 
 - CRUD ์ฟผ๋ฆฌ๋ PREPARED๋ STATEMENT๋ฅผ ์ฌ์ฉํ์ง๋ง FUNCTION์ด๋ PROCEDURE ์ฌ์ฉ์์๋ CALLABLE ์ฌ์ฉ
  ```sql
  <!DOCTYPE mapper PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"  "http://mybatis.org/dtd/mybalis-3-mapper.dtd">
  <mapper namespace="testMapper" >

    <select id="getValues" parameterType="paramVO" returnType="paramVO" statementType="CALLABLE">
        { call testProc(
                    #{inParam01, mode=IN, jdbcType=VARCHAR}
                  , #{inParam02, mode=IN, jdbcType=VARCHAR}
                  , #{outParam01, mode=OUT, jdbcType=VARCHAR}
                  , #{outParam01, mode=OUT, jdbcType=VARCHAR}
                  , #{outParam01, mode=OUT, jdbcType=VARCHAR})
        }
    </select>
  </mapper>
  ```   

  ```sql
  paramVO vo = new paramVO();
  vo.setInParam01("value1");
  vo.setInParam02("value2");
  testService.getValues(vo);

  System.out.print("First return value : " + vo.getOutParam01());
  ```                                     
                                                        
                                                        



