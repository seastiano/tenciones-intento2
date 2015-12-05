# tenciones-intento2
proyecto de longitud minima y tenciones 
%Funcion tensiones
syms t1 t2;
lacmin=0;
for lac (0:0.1:6.7)
    
    theta=acosd((47-(lac^2))/36)%Ecuacion para hallar theta con los valores conocidos
    phi=asind(3*sin(theta)/lac) %Ecuacion para hallar phi con los valores conocidos     
    [t1,t2]=solve('-t1*cos(theta)+t2*cos(phi)==0','t2+sin(phi)+(t1*sin(theta))==2000'); %Funcion Solve para despejar las tensiones
    
    if (t1>2000 | t2>2000)% Condicion de que las tensiones no sobrepasen 2000 lb
        lacmin==lac% Lacmin toma el valor de Lac en el momento en que alguna de las tensiones supere 2000 lb
    end
    plot(t1,lac)
    plot(t2,lac)
    

end 

