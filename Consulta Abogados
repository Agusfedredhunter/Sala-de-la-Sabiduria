-- 1: Cuál es el nombre y la dirección de los procuradores que han trabajado en un asunto abierto?

select
 p.nombre,
 p.direccion
from Procuradores P 
join 
 Asuntos_procuradores ap on p.id_procurador= ap.id_procurador
join 
 asuntos a on ap.numero_expediente =a.numero_expediente
where
 a.estado='abierto';

-- 2: Qué clientes han tenido asuntos en los que ha participado el procurador Carlos López?

select distinct
 c.nombre as clientes,
 c.dni,
 a.numero_expediente
from
 Clientes c
 JOIN
    Asuntos A ON C.dni = A.dni_cliente
join
 asuntos_procuradores ap on a.numero_expediente = ap.numero_expediente
join 
 procuradores p on ap.id_procurador = p.id_procurador
where
 p.nombre ='Carlos Lopez';

-- 3: Cuántos asuntos ha gestionado cada procurador?

select
 p.nombre as nombre_procurador,
 count(ap.numero_expediente) as cantidad_asuntos
 from
  procuradores p
join 
 asuntos_procuradores ap on p.id_procurador = ap.id_procurador
group by
 p.nombre
order by
 cantidad_asuntos desc, p.nombre;

-- 4: Lista los números de expediente y fechas de inicio de los asuntos de los clientes que viven en Buenos Aires.

select
 a.numero_expediente,
 a.fecha_inicio
from
 asuntos a
join 
 clientes c  on a.dni_cliente=c.dni
where
 c.direccion like '%buenos aires%';
