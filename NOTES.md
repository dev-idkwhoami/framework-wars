# Notes
> [!NOTE]
> These notes are just a stream of conciousness as I develop this.
> This  is not documentation and is probably not accurate as to what is implemented

what causes stocks to be created?
- random event throughout the day
- when a new player joins IE an account gets created we create stock in their location
  -- potential problems of doing it
      * players can abuse this to create inventory
  -- potential solutions
     * players spawn in a random location so gaming it is hard
  -- do we like this trade-off??

- how much should we seed the game with?
  -- we want supply and demmand throught different regions with different inventory
     -- do we just wing it?
  -- do we want overall inventory equal to start?
     * IE react has 500 across regions vue has 500 across regions etc etc


    location_snapshot {
        id
        user_id
        location_id
        elements
            {react: 5, vue: {qty: 10, price: 50}}
        created_at:
    }

   x  framework_unit {
         id
         framework_id

         location_id (only has value if no user_id)
         user_id (only has value if user_id)
         trades
     }

     UPDATE framework_unit where framework_id = id WHERE location_id LIMIT 10

     SELECT * from framework_unit WHERE location_id = "x";

    x trade_table {
         user_id index
         location_id index
         direction "BUY" | "SELL" index
         price
         ammt
         hasMany framework_ids
     }