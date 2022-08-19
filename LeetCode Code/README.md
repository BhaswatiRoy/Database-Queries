`1757. Recyclable and Low Fat Products`

       SELECT PRODUCT_ID FROM PRODUCTS WHERE LOW_FATS='Y' AND RECYCLABLE='Y';

`175. Combine Two Tables`

      # left join as left table-person is 
      SELECT PERSON.firstname, PERSON.lastname, ADDRESS.city, ADDRESS.state 
      FROM PERSON LEFT JOIN ADDRESS
      ON PERSON.PERSONID=ADDRESS.PERSONID
