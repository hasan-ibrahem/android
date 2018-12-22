السسسسسؤال الخامس  ************ 


---5------------------------------------------------------
create  VIEW [dbo].[view_alldata]
AS
SELECT dbo.flight.flight_id, dbo.pilot.pilot_name, dbo.plane.plane_name, dbo.flight.flight_date, dbo.flight.fight_hours
FROM     dbo.flight INNER JOIN
                  dbo.pilot ON dbo.flight.pilot_id = dbo.pilot.pilot_id AND dbo.flight.pilot_id = dbo.pilot.pilot_id INNER JOIN
                  dbo.plane ON dbo.flight.plane_name = dbo.plane.plane_name
				  where dbo.flight.flight_date in (GETDATE())

GO


