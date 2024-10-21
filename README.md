# 1.2 Instalación de zonas mestras primarias en Windows Server

1. Instala o servidor DNS no equipo lukeskywalker. Comproba que xa funciona coma servidor DNS caché pegando no documento de entrega a saída deste comando  nslookup -norecurse "www.starwars.com" localhost.

   ![img](Images/ej1.1.png)

2. Configura o servidor DNS para que empregue como reenviador 8.8.8.8. pegando no documento de entrega a captura de pantalla da configuración do reenviador e a saída deste comando: nslookup -recurse "www.starwars.com" localhost

   ![img](Images/ej2.1.png)

   ![img](Images/ej2.2.png)

3. Instala unha zona primaria de resolución directa chamada "academia.jedi" e engade os seguintes rexistros de recursos (a maiores dos rexistros NS e SOA imprescindibles):
   - Tipo A: lukeskywalker con IP 192.168.20.101
   - Tipo A: benskywalker con IP 192.168.20.102
   - Tipo A: obiwankenobi con IP 192.168.56.152 e 192.168.56.153
   - Tipo A: hansolo con IP 192.168.56.105
   - Tipo A: leia con IP 192.168.56.106
   - Tipo A: anakinsolo con IP 192.168.56.106
   - Tipo CNAME mestrejedi a obiwankenobi
   - TIPO MX con prioridade 10 sobre o equipo hansolo
   - TIPO TXT "thon" con "un Jedi debe sentir a tensión entre os dous lados da Forza"
   - TIPO NS con benskywalker
   - Pega no documento de entrega a captura dos rexistros creados

   ![img](Images/ej3.1.png)

4. Instala unha zona de resolución inversa que teña que ver co enderezo do equipo lukeskywalker, e engade rexistros PTR para os rexistros tipo A do exercicio anterior. Pega no documento de entrega o a captura dos rexistros da zona.

   ![img](Images/ej4.1.png)

   ![img](Images/ej4.2.png)

5. Comproba que podes resolver os distintos rexistros de recursos. Pega no documento de entrega a saída dos comandos:

   - nslookup lukeskywalker.academia.jedi localhost

   ![img](Images/ej5.1.png)

   - nslookup hansolo.academia.jedi localhost

   ![img](Images/ej5.2.png)

   - nslookup leia.academia.jedi localhost

   ![img](Images/ej5.3.png)

   - nslookup anakinsolo.academia.jedi localhost

   ![img](Images/ej5.4.png)

   - nslookup academia.jedi localhost

   ![img](Images/ej5.5.png)

   - nslookup -q=mx academia.jedi localhost

   ![img](Images/ej5.6.png)

   - nslookup -q=ns academia.jedi localhost

   ![img](Images/ej5.7.png)

   - nslookup -q=soa academia.jedi localhost

   ![img](Images/ej5.8.png)

   - nslookup -q=txt thon.academia.jedi localhost

   ![img](Images/ej5.9.png)

   - nslookup 192.168.20.101 localhost

   ![img](Images/ej5.10.png)
