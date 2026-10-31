
GRANT pg_monitor TO postgres;


CREATE USER postgres WITH PASSWORD 'Logicmo_2020';
GRANT pg_monitor TO postgres;


host    postgres  monitor   192.168.1.100/32   scram-sha-256
# TYPE  DATABASE  USER      ADDRESS            METHOD
--add in booth svr 
host    postgres  postgres  192.168.1.100/32   scram-sha-256
host    postgres  monitor   192.168.1.100/32   scram-sha-256

SELECT pg_reload_conf();

"ConnectionStrings": {
  "Primary": "Host=192.168.1.100;Port=5432;Database=postgres;Username=monitor;Password=Logicmo_2020;Timeout=5",
  "Standby": "Host=192.168.1.102;Port=5432;Database=postgres;Username=monitor;Password=Logicmo_2020;Timeout=5"
}
