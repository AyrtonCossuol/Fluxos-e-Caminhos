#SETS
set N;
set A within {N,N};

#Parametros
param w{A} >= 0;
param S{N} >= 0;
param D{N} >= 0;

#Variavel
var x{A} >= 0;

#Objetivo
minimize cost: sum{(i,j) in A} w[i,j]*x[i,j];
 
#Constante
s.t. flow{i in N}: S[i] + sum{(j,i) in A} x[j,i] = D[i] + sum{(i,j) in A} x[i,j];
