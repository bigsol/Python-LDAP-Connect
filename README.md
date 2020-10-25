# Python-LDAP-Connect


import json
from ldap3 import Server, Connection, NTLM, ALL

USER="domain\\username"
<br>myuser = 'username'
<br>ldappw = 'password'
<br>
<br>ldapserver='ldap://x.x.x.x'
<br>
<br>dn='CN=XXX,OU=XXX,OU=XXX,DC=domain,DC=com'
<br>cn = "DC=domain,DC=XXX"
<br>
<br>ldapconn=Connection(ldapserver,auto_bind=True, user=USER, password=ldappw, authentication=NTLM)
<br>ldapconn.bind()
<br>
<br>my_filter = '(sAMAccountName='+myuser+')' 
<br>ldapconn.search(dn, my_filter, attributes=['mail','cn','displayName','givenName','userPrincipalName','sAMAccountName'])
<br>user_email = str(ldapconn.response[0]['attributes']['mail'])
<br>
<br>user_cn = str(ldapconn.response[0]['attributes']['sAMAccountName'])
<br>
<br>print("Found user:", json.dumps(user_cn))
<br>
<br>ldapconn.unbind()
<br>
<br>
<br>


<p><a href="hhttps://docs.secureauth.com/display/KBA/Active+Directory+Attributes+List/">Active Directory Attributes List!</a></p>

