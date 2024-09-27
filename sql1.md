Code 1
SELECT*
FROM crime_scene_report where type=&#39;murder&#39; and city=&#39;SQL City&#39; and
date=20180115

Code 2
SELECT*
FROM person where address_street_name=&#39;Northwestern Dr&#39; or&#39;Franklin
Ave&#39;
Then
SELECT *
FROM person where address_street_name=&#39;Northwestern Dr&#39;ORDER BY
address_number DESC
limit 1

Code 3
SELECT*
FROM person where name like &#39;%Annabel%&#39; and
address_street_name=&#39;Franklin Ave&#39;

Code 4
SELECT *
FROM interview where person_id=14887
Code 5
SELECT *
FROM interview where person_id=16371


Code 6
SELECT *
FROM get_fit_now_member
where person_id=16371

Code 7
SELECT *
FROM get_fit_now_check_in
where check_in_date=20180109 and membership_id like&#39;%48Z%&#39;

Code 8
SELECT *
FROM get_fit_now_member
WHERE id = &#39;48Z7A&#39; OR id = &#39;48Z55&#39;;

Code 9
SELECT *
FROM drivers_license
where plate_number like &#39;%H42W%&#39;

Code 10
SELECT *
FROM person
where license_id=423327 or license_id=664760


FINAL ANSWER FOR MURDER

SELECT *
FROM person
WHERE (license_id=423327 OR license_id=664760) AND (id=67318 OR
id=28819);
