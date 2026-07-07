
#### Si descriva nel dettaglio la variabile MIB ipAddrTable. Spiegare il meccanismo di accesso ai dati della tabella che usa i suffissi.

---

```
;definisce una variabile ip. Definisce il 20esimo elemento del nodo IP
ipAddrTable OBJECT-TYPE
	SYNTAX      SEQUENCE OF IpAddrEntry
	MAX-ACCES   not-accessible
	STATUS      current
	DESCRIPTION "The table of addressing information relevant to this                              entity's IP addresses"
	::={ ip 20 }

;oggetto 	
ipAddrEntry OBJECT-TYPE
	SYNTAX      IpAddrEntry
	MAX-ACCES   not-accessible
	STATUS      current
	DESCRIPTION "The addressing information for one of this entity's IP                          addresses"
	INDEX       { ipAdEntAddr }
	::={ ipAddrTable 1 }

IpAddrEntry ::=SEQUENCE {
	ipAdEntAddr         IpAddress,
	ipAdEntIfIndex      INTEGER,
	ipAdEntNetMask      IpAddress,
	ipAdEntBcastAddr    INTEGER,
	ipAdEntReasmMaxSize INTEGER
}

ipAddEntAddr OBJECT-TYPE
	SYNTAX      IpAddress
	MAX-ACCES   read-only
	STATUS      current
	DESCRIPTION "The IP address to which this entry's addressing information                      pertain"
	::={ ipAddrTable 1 }
```