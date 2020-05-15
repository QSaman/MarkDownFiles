# Timezone

* What is the date-time in Montreal next Saturday at 20:30 in Tehran?

```
$ TZ="America/Montreal" date -d 'TZ="Asia/Tehran" next saturday 20:30'
Sat May 16 12:00:00 EDT 2020
```

* Printing the current timezone in Vancouver and its offset from UTC:

```
$ TZ="America/Vancouver" date "+%Z = %:z"
PDT = -07:00
```
* Listing all timezones:

```
timedatectl list-timezones
```
or

```
$ ls /usr/share/zoneinfo/America/
Adak            Barbados       Catamarca      Dawson        Glace_Bay   Indiana       Los_Angeles    Merida       Nome            Puerto_Rico   Santo_Domingo  Tegucigalpa
Anchorage       Belem          Cayenne        Dawson_Creek  Godthab     Indianapolis  Louisville     Metlakatla   Noronha         Punta_Arenas  Sao_Paulo      Thule
Anguilla        Belize         Cayman         Denver        Goose_Bay   Inuvik        Lower_Princes  Mexico_City  North_Dakota    Rainy_River   Scoresbysund   Thunder_Bay
Antigua         Blanc-Sablon   Chicago        Detroit       Grand_Turk  Iqaluit       Maceio         Miquelon     Ojinaga         Rankin_Inlet  Shiprock       Tijuana
Araguaina       Boa_Vista      Chihuahua      Dominica      Grenada     Jamaica       Managua        Moncton      Panama          Recife        Sitka          Toronto
Argentina       Bogota         Coral_Harbour  Edmonton      Guadeloupe  Jujuy         Manaus         Monterrey    Pangnirtung     Regina        St_Barthelemy  Tortola
Aruba           Boise          Cordoba        Eirunepe      Guatemala   Juneau        Marigot        Montevideo   Paramaribo      Resolute      St_Johns       Vancouver
Asuncion        Buenos_Aires   Costa_Rica     El_Salvador   Guayaquil   Kentucky      Martinique     Montreal     Phoenix         Rio_Branco    St_Kitts       Virgin
Atikokan        Cambridge_Bay  Creston        Ensenada      Guyana      Knox_IN       Matamoros      Montserrat   Port-au-Prince  Rosario       St_Lucia       Whitehorse
Atka            Campo_Grande   Cuiaba         Fortaleza     Halifax     Kralendijk    Mazatlan       Nassau       Porto_Acre      Santa_Isabel  St_Thomas      Winnipeg
Bahia           Cancun         Curacao        Fort_Nelson   Havana      La_Paz        Mendoza        New_York     Port_of_Spain   Santarem      St_Vincent     Yakutat
Bahia_Banderas  Caracas        Danmarkshavn   Fort_Wayne    Hermosillo  Lima          Menominee      Nipigon      Porto_Velho     Santiago      Swift_Current  Yellowknife

```

* The current timezone:

```
$ ls -l /etc/ | grep -i localtime
lrwxrwxrwx.  1 root root        37 Jan 23 23:37 localtime -> ../usr/share/zoneinfo/America/Toronto
```

or

```
$ $ timedatectl | grep -i "time zone:"
Time zone: America/Toronto (EDT, -0400)

$ date +%Z
EDT
```

