السؤاااااال السااادس







/*create   VIEW [dbo].[view_alldata]
AS
SELECT dbo.flight.flight_id, dbo.pilot.pilot_name, dbo.plane.plane_name, dbo.flight.flight_date, dbo.flight.fight_hours
FROM     dbo.flight INNER JOIN
                  dbo.pilot ON dbo.flight.pilot_id = dbo.pilot.pilot_id AND dbo.flight.pilot_id = dbo.pilot.pilot_id INNER JOIN
                  dbo.plane ON dbo.flight.plane_name = dbo.plane.plane_name
				  where dbo.flight.flight_date in (GETDATE())


GO*/



create trigger myinsteadoftrigger
on [dbo].[view_alldata]
instead of insert
as
begin
declare @pilot_name nvarchar(15)
declare @plane_name nvarchar(15)
declare @flight_date date
declare @fight_hours int

select @pilot_name=I.pilot_name,@plane_name=I.plane_name,@flight_date=I.flight_date,@fight_hours=I.fight_hours
from inserted I INNER JOIN
                  dbo.pilot ON dbo.flight.pilot_id = dbo.pilot.pilot_id AND dbo.flight.pilot_id = dbo.pilot.pilot_id INNER JOIN
                  dbo.plane ON dbo.flight.plane_name = dbo.plane.plane_name
				  where dbo.flight.flight_date in (GETDATE()) 

				  insert into  dbo.pilot( pilot_name) values(@pilot_name)
				  insert into dbo.plane(plane_name) values (@plane_name)
end



insert into [dbo].[view_alldata] values('F15478','WGGGG','PLAAAA',26/5/2018,5)
