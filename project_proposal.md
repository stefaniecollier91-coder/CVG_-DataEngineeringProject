
digraph ERD {
    graph [rankdir=LR, bgcolor="white", margin=0.2, nodesep=0.6, ranksep=0.9];
    node [shape=plain, fontname="Arial"];
    edge [fontname="Arial", fontsize=10, color="#555555"];

    airport [label=<
    <TABLE BORDER="1" CELLBORDER="1" CELLSPACING="0" CELLPADDING="6">
      <TR><TD BGCOLOR="#D9EAF7"><B>airport</B></TD></TR>
      <TR><TD ALIGN="LEFT">PK airport_id</TD></TR>
      <TR><TD ALIGN="LEFT">airport_code</TD></TR>
      <TR><TD ALIGN="LEFT">airport_name</TD></TR>
      <TR><TD ALIGN="LEFT">city</TD></TR>
      <TR><TD ALIGN="LEFT">state</TD></TR>
      <TR><TD ALIGN="LEFT">latitude</TD></TR>
      <TR><TD ALIGN="LEFT">longitude</TD></TR>
    </TABLE>>];

    airline [label=<
    <TABLE BORDER="1" CELLBORDER="1" CELLSPACING="0" CELLPADDING="6">
      <TR><TD BGCOLOR="#D9EAF7"><B>airline</B></TD></TR>
      <TR><TD ALIGN="LEFT">PK airline_id</TD></TR>
      <TR><TD ALIGN="LEFT">carrier_code</TD></TR>
      <TR><TD ALIGN="LEFT">carrier_name</TD></TR>
    </TABLE>>];

    date_month [label=<
    <TABLE BORDER="1" CELLBORDER="1" CELLSPACING="0" CELLPADDING="6">
      <TR><TD BGCOLOR="#D9EAF7"><B>date_month</B></TD></TR>
      <TR><TD ALIGN="LEFT">PK month_id</TD></TR>
      <TR><TD ALIGN="LEFT">month_start_date</TD></TR>
      <TR><TD ALIGN="LEFT">year_number</TD></TR>
      <TR><TD ALIGN="LEFT">month_number</TD></TR>
      <TR><TD ALIGN="LEFT">month_name</TD></TR>
      <TR><TD ALIGN="LEFT">season</TD></TR>
    </TABLE>>];

    flight [label=<
    <TABLE BORDER="1" CELLBORDER="1" CELLSPACING="0" CELLPADDING="6">
      <TR><TD BGCOLOR="#FCE4D6"><B>flight_monthly_performance</B></TD></TR>
      <TR><TD ALIGN="LEFT">PK performance_id</TD></TR>
      <TR><TD ALIGN="LEFT">FK airport_id</TD></TR>
      <TR><TD ALIGN="LEFT">FK airline_id</TD></TR>
      <TR><TD ALIGN="LEFT">FK month_id</TD></TR>
      <TR><TD ALIGN="LEFT">on_time_arrivals</TD></TR>
      <TR><TD ALIGN="LEFT">arrival_delays</TD></TR>
      <TR><TD ALIGN="LEFT">flight_cancelled</TD></TR>
      <TR><TD ALIGN="LEFT">diverted_flights</TD></TR>
      <TR><TD ALIGN="LEFT">flight_operations</TD></TR>
    </TABLE>>];

    weather [label=<
    <TABLE BORDER="1" CELLBORDER="1" CELLSPACING="0" CELLPADDING="6">
      <TR><TD BGCOLOR="#E2F0D9"><B>weather_daily</B></TD></TR>
      <TR><TD ALIGN="LEFT">PK weather_id</TD></TR>
      <TR><TD ALIGN="LEFT">FK airport_id</TD></TR>
      <TR><TD ALIGN="LEFT">weather_date</TD></TR>
      <TR><TD ALIGN="LEFT">temperature_avg_f</TD></TR>
      <TR><TD ALIGN="LEFT">precipitation_inches</TD></TR>
      <TR><TD ALIGN="LEFT">snowfall_inches</TD></TR>
      <TR><TD ALIGN="LEFT">wind_speed_avg_mph</TD></TR>
      <TR><TD ALIGN="LEFT">severe_weather_flag</TD></TR>
    </TABLE>>];

    etl [label=<
    <TABLE BORDER="1" CELLBORDER="1" CELLSPACING="0" CELLPADDING="6">
      <TR><TD BGCOLOR="#EADCF8"><B>etl_run_log</B></TD></TR>
      <TR><TD ALIGN="LEFT">PK run_id</TD></TR>
      <TR><TD ALIGN="LEFT">run_name</TD></TR>
      <TR><TD ALIGN="LEFT">source_system</TD></TR>
      <TR><TD ALIGN="LEFT">run_status</TD></TR>
      <TR><TD ALIGN="LEFT">records_loaded</TD></TR>
    </TABLE>>];

    airport -> flight [label="1 to many"];
    airline -> flight [label="1 to many"];
    date_month -> flight [label="1 to many"];
    airport -> weather [label="1 to many"];
}
