-- Consultas sin Join

-- 1: Qué socios tienen barcos amarrados en un número de amarre mayor que 10?

select 
  nombre
from 
  socios
where
  id_socio in (
       select
         id_socio
	   from
         barcos
	   where
        numero_amarre>10
	);

-- 2: Cuáles son los nombres de los barcos y sus cuotas de aquellos barcos cuyo socio se llama 'Juan Pérez'?

select nombre, cuota
from barcos
where id_socio =(
    select id_socio
    from Socios
    where nombre = 'Juan Perez'
);

-- 3: Cuántas salidas ha realizado el barco con matrícula 'ABC123'?

select 
  count(*) as total_salidas
from 
 salidas
where
 matricula= 'ABC123';

-- 4: Lista los barcos que tienen una cuota mayor a 500 y sus respectivos socios.

select 
 b.nombre as nombre_barco,
 b.cuota,
 (select 
  s.nombre
from 
 socios s
where 
 s.id_socio=b.id_socio)
 as nombre_socio
 from 
  barcos b
  where
   b.cuota>500.00;

-- 5: Qué barcos han salido con destino a 'Mallorca'?

select 
 nombre
from
 barcos
where 
 matricula in (
         select
          matricula
		from
         salidas
         where
         destino='mallorca'
);

-- 6: Qué patrones (nombre y dirección) han llevado un barco cuyo socio vive en 'Barcelona'?
select 
  patron_nombre,
  patron_direccion
from
  salidas
where
  matricula in (
      select
        matricula
	  from
        barcos
	  where
        id_socio in (
           select
             id_socio
		   from
              socios
			where
              direccion like '%barcelona%'
              )
);

-- Consultas sin Join

-- 1: Qué socios tienen barcos amarrados en un número de amarre mayor que 10?

select 
 s.nombre
from
 socios s 
join
 barcos b on s.id_socio =b.id_socio
where
 b.numero_amarre>10;

-- 2: Cuáles son los nombres de los barcos y sus cuotas de aquellos barcos cuyo socio se llama 'Juan Pérez'?

select
 b.nombre,
 b.cuota
from
 barcos b
join
 socios s on b.id_socio=s.id_socio
where
 s.nombre = 'juan perez';

-- 3: Cuántas salidas ha realizado el barco con matrícula 'ABC123'?

select
 count(*) as total_salidas
from
 salidas
where
 matricula = 'abc123';

-- 4: Lista los barcos que tienen una cuota mayor a 500 y sus respectivos socios.

select
 b.nombre as nombre_barco,
 b.cuota,
 s.nombre as nombre_socio
from
 barcos b
join
 socios s on b.id_socio = s.id_socio
where
 b.cuota >500.00;

-- 5: Qué barcos han salido con destino a 'Mallorca'?

select 
 b.nombre as barco
from
 barcos b
join
 salidas s on b.matricula =s.matricula
where
 s.destino ='mallorca';

-- 6: Qué patrones (nombre y dirección) han llevado un barco cuyo socio vive en 'Barcelona'?

select
 s.patron_nombre,
 s.patron_direccion
from
 salidas s 
join
 barcos b on s.matricula =b.matricula
join
 socios so on b.id_socio = so.id_socio
where
 so.direccion like '%barcelona%';

