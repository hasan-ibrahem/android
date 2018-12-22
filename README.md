 ********السؤاااال الرابع





create trigger tr_flight_oninsert
on  [dbo].[flight]
after insert
as
begin
declare @flightenterednumber  int 
select  @flightenterednumber =[fight_hours]from inserted
 UPDATE [dbo].[flight] SET [fight_hours]=[fight_hours]+@flightenterednumber

end
