# 🤓 SQL 레벨업!!
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
  
</details> 


