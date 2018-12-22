a.


SELECT fight_hours AS Expr1, dbo.flight.*
FROM     dbo.flight
where fight_hours >10 and DATEDIFF(year, flight_date,getDate()) in (2018);
 --------------------------------------------------------------------
 b.
 
 
  SELECT dbo.pilot.pilot_name
FROM     dbo.pilot INNER JOIN
                  dbo.flight ON dbo.pilot.pilot_id = dbo.flight.pilot_id AND dbo.pilot.pilot_id = dbo.flight.pilot_id

				   where fight_hours >10 and DATEDIFF(year, flight_date,getDate()) in (2018);
				   --------------------------------------------------
				   
c.

SELECT  dbo.pilot.pilot_name
FROM     dbo.pilot CROSS JOIN
                  dbo.plane
				  
				  where   dbo.plane.plane_name='palestine800';
				  
				-------------------------------------  ---------------------------------
				  d.
				  
				  SELECT dbo.flight.flight_id
FROM     dbo.flight INNER JOIN
                  dbo.pilot ON dbo.flight.pilot_id = dbo.pilot.pilot_id AND dbo.flight.pilot_id = dbo.pilot.pilot_id
				  where DATEDIFF(year,dbo.pilot.dob,getdate()) >45 
				and dbo.flight.fight_hours between  10000 and 20000
				---------------------
				  
	e.			  SELECT avg(hoursflown)
FROM     dbo.plane
where dbo.plane.plane_name='military'
