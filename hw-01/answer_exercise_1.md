------------------------------------------------------------------------------
  ## Indica la diferencia entre el uso de la instrucción CMD y ENTRYPOINT ##
------------------------------------------------------------------------------
 
 -- CMD --
  
Define comandos y/o parámetros predeterminados para un contenedor. Es una instrucción que se usa si se necesita un comando predeterminado que los usuarios pueden anular fácilmente. 

La instrucción CMD solo se utiliza si no se agrega ningún argumento al comando run al iniciar un contenedor. Por lo tanto, si el contenedor Docker ya se ejecuta con un comando, se ignorará el comando predeterminado de CMD.

Si un Dockerfile tiene varias CMD, solo se aplicará la última instrucción.

CMD tiene tres formas:
 - CMD ["executable","param1","param2"] (forma ejecutiva)
 - CMD ["param1","param2"](como parámetros predeterminados para ENTRYPOINT en forma ejecutiva)
 - CMD command param1 param2 (forma de concha)

-- ENTRYPOINT --
Permite configurar cómo se ejecutará el contenedor. Se usa ENTRYPOINT cuando se desea definir un contenedor con un ejecutable específico.

La diferencia con CMD es que no puede anular la instrucción ENTRYPOINT agregando parámetros en la linea de comandos de run. Al optar por esta instrucción, implica que el contenedor está diseñado específicamente para ese uso.

ENTRYPOINT tiene dos formas:
 - ENTRYPOINT ["executable","param1","param2"] (forma ejecutiva)
 - ENTRYPOINT command param1 param2 (forma de concha)



ENTRYPOINT y CMD son similares pero no iguales, y no se excluyen mutuamente, es posible tener los dos en un Dockerfile.

Se combinan ENTRYPOINT y CMD cuando se necesita un contenedor con un ejecutable especificado y un parámetro predeterminado que se pueda modificar fácilmente. 
Si se utilizan ambas instrucciones, hay que mantenerlas en formato ejecutivo.
