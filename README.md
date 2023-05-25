# rasp_spin
import math
h_init = 0.5  #metre cinsinden borunun ortasının yuksekliği
V_init = 4 #m/s cinsinden lazerden gelen değer
g = 9.8 #yercekimi ivm
teta = 7 #verdiğimiz angle in degree
r = 0.02 #in meters
t_ball_on_our_side = 3  #ball measured time from img prcss
t_sbt = 0.7
m = 2.7/1000
t_real_flight = t_ball_on_our_side - t_sbt #aslında topun uçus süresi assmp

t_cikis= V_init*math.sin(math.radians(teta)) / g
h_max = h_init + (V_init*math.sin(math.radians(teta)) * t_cikis /2) #çıktığıpeak
t_inis = math.sqrt(2*h_max/g)
t_deflect =(t_cikis + t_inis ) -t_real_flight
E_spn = (t_deflect*t_deflect)*g*g/2*m
print(E_spn)
V_downward = t_inis * g
V_lateral = V_init * math.cos(math.radians(teta))
V_last = math.sqrt(V_downward*V_downward + V_lateral * V_lateral)
print(h_max, V_lateral )
E_init = (V_init*V_init)/2 + g * h_init
E_last = (V_last * V_last)/2
E_spin = E_init - E_last
print(E_spin)
#w_spin = math.sqrt(5*E_spin/(r*r))

