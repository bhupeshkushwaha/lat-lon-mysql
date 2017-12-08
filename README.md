# lat-lon-mysql


select id, 
       ( 3959 * acos( cos( radians(43.653226) ) 
              * cos( radians( SUBSTRING_INDEX(latitude_longitude,',',1) ) ) 
              * cos( radians( SUBSTRING_INDEX(latitude_longitude,',',-1) ) - radians(-79.383184) ) 
              + sin( radians(43.653226) ) 
              * sin( radians( SUBSTRING_INDEX(latitude_longitude,',',1) ) ) ) ) AS distance 
from restaurant
