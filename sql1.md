Code 1
SELECT *
FROM crime_scene_report where type=&#39;murder&#39; and city=&#39;SQL City&#39; and
date=20180115
Output
Security footage shows that there were 2 witnesses. The first witness
lives at the last house on &quot;Northwestern Dr&quot;. The second witness, named
Annabel, lives somewhere on &quot;Franklin Ave&quot;.

Code 2
SELECT *
FROM person where address_street_name=&#39;Northwestern Dr&#39; or&#39;Franklin
Ave&#39;
Then
SELECT *
FROM person where address_street_name=&#39;Northwestern Dr&#39;ORDER BY
address_number DESC
limit 1
output
14887 Morty Schapiro 118009 4919 Northwestern Dr 111564949

Code 3
SELECT *
FROM person where name like &#39;%Annabel%&#39; and
address_street_name=&#39;Franklin Ave&#39;
Output
16371 Annabel Miller 490173 103 Franklin Ave 318771143

Code 4
SELECT *
FROM interview where person_id=14887
Output
I heard a gunshot and then saw a man run out. He had a &quot;Get Fit Now Gym&quot;
bag. The membership number on the bag started with &quot;48Z&quot;. Only gold
members have those bags. The man got into a car with a plate that
included &quot;H42W&quot;.

Code 5
SELECT *
FROM interview where person_id=16371
Output
I saw the murder happen, and I recognized the killer from my gym when I
was working out last week on January the 9th.

Code 6
SELECT *
FROM get_fit_now_member
where person_id=16371
output
90081 16371 Annabel Miller 20160208 gold

Code 7
SELECT *
FROM get_fit_now_check_in
where check_in_date=20180109 and membership_id like&#39;%48Z%&#39;
Output
---48Z7A 20180109 1600 1730
---48Z55 20180109 1530 1700

Code 8
SELECT *
FROM get_fit_now_member
WHERE id = &#39;48Z7A&#39; OR id = &#39;48Z55&#39;;
Output
48Z55 67318 Jeremy Bowers 20160101 gold
48Z7A 28819 Joe Germuska 20160305 gold

Code 9
SELECT *
FROM drivers_license
where plate_number like &#39;%H42W%&#39;
output
183779 21 65 blue blonde female H42W0X Toyota
Prius
423327 30 70 brown brown male 0H42W2 Chevrolet Spark LS
664760 21 71 black black male 4H42WR Nissan Altima

Code 10
SELECT *
FROM person
where license_id=423327 or license_id=664760
output
51739 Tushar Chandra 664760 312 Phi St 137882671
67318 Jeremy Bowers 423327 530 Washington Pl, Apt 3A 871539279

FINAL ANSWER FOR MURDER

SELECT *
FROM person
WHERE (license_id=423327 OR license_id=664760) AND (id=67318 OR
id=28819);
output
id name license_id address_number address_street_name ssn
67318 Jeremy Bowers 423327 530 Washington Pl, Apt 3A 871539279
