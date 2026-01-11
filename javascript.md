# Opening examples

## From Dwitter

Title: Spiral Galaxy

Creator: **@marquisdegeek**

URL: https://www.dwitter.net/d/33914
```
c.width|=\nr=_=>Math.random()*_\nfor(n=2e4;--n;)A=r(1),B=r(10),U=400*A*S(B),V=50*A*C(B),P=frame/25+10*A,D=C(P),N=S(P),G=U*D+V*N,H=-U*N+V*D,x.fillRect(3*(320+G+H*.3),2*(240-G*.2+H*.4),2,2);
```


## From twigl.app
Title: **Shader caves**

Creator: **@h_doxas**

URL: https://twigl.app/?ss=-OQFZ_REMELj-TU9KqN0
```
vec3 q=vec3(0,0,1e4),v=FC.gbr-r.yxx*.3,p;for(float i,s,d;i++<53.;d=.2*t){for(p=q,s=6e3;4.<s;p=p.zxy-s*sin(p/s*6.3)*.05,s*=d=.8)p.yz*=rotate2D(d);d=length(vec2(length(p.yz)-1e4,p.x))-3e3;v.x+=v.x*step(7e2,q.x)*(1.1-mod(FC.y,2.)*2.);q+=sin(i)+v/r.x*d;o+=exp(-d*d/vec4(3,2,1,1))/i;}
```



# Low hanging fruit - text


## Remove whitespace

| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 8 | return 1 | return1 | 7 | 


| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 10 | return 0.1 | return .1 | 9 | 
| 9 | return .1 | return.1 | 8 | 
| 9 | typeof [] | typeof[] | 8 | 


## Remove constants

| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 4 | 0xff | 255 | 3 |
| 5 | 40000 | 4e4 | 3 |
| 12 | rgb(255,0,0) | "#FF0000" | 9 |
| 9 | "#FF0000" | "red" | 5 |

## Compression

Title: **Starpath**

Creator: **HellMood/Desire and @marquisdegeek**

URL: https://www.dwitter.net/d/33418
```
M=t?M+1:0;for(F=255,P=F*F;--P;x.fillStyle=c,x.fillRect(X*8,y*5,8,5))for(X=P%F,y=P/F,c=0,D=9;!c;++D)v=X-D,c=v<0?(((y*D&F)+y+X&F)==0)?R(F,F,F):R(C,y,y):(K=(y*D>>8|v*D>>8)&D+M,K&16?R(K*=4,K,K):0)
```
Compresses to:
```
eval(unescape(escape`󣜽󭌿󣜫󜜺󜌻󩭯󬬨󡬽󜬵󝜬󤌽󡬪󡬻󛜭󤌻󮌮󩭩󫍬󤽴󮝬󩜽󨼬󮌮󩭩󫍬󤭥󨽴󚍘󚬸󛍹󚬵󛌸󛌵󚜩󩭯󬬨󦌽󤌥󡬬󮜽󤌯󡬬󨼽󜌬󡌽󞜻󘝣󞼫󚽄󚝶󟝘󛝄󛍣󟝶󟌰󟼨󚌨󮜪󡌦󡬩󚽹󚽘󙭆󚜽󟜰󚜿󤬨󡬬󡬬󡬩󞭒󚍃󛍹󛍹󚜺󚍋󟜨󮜪󡌾󟬸󯍶󚭄󟬾󞌩󙭄󚽍󛍋󙬱󝬿󤬨󢼪󟜴󛍋󛍋󚜺󜌩`.replace(/u../g,'')))
```


# Low hanging fruit - Code

## True / false

| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 4 | true | 1 | 1 |
| 5 | false | 0 | 1 |


| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 4 | true | !0 | 2 |
| 5 | false | !1 | 2 |

Rem: Use == not === because 1==true is true, but 1===true is false

## First-class citizens

| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 8 | Math.sin | S=Math.sin | 10 |
| 8 | Math.sin | with(Math) | 10 |
| 8 | Math.pow | P=Math.pow | 10 |
| 4 | Math | M=Math | 6 |
| 8 | Math.pow | M.pow | 5 |

| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 10 | M.pow(a,b) | a**b | 4 |
| 10 | M.pow(a,3) | a\*a\*a | 5 |
| 9 | M.sqrt(2) | 2**.5 | 5 |

## Example

Title: **Cemetery of Deleted Dweets**

Creator: **@rodrigo.siqueira**

URL: https://www.dwitter.net/d/33102

```
for(R=i=1920*(t<5);i;Y|+.13<C(a=X*2%4-2)*.1*C(b=T*2%2.5-1)|a*a+b**4<Y/9|Y>1+T%3/64|T>6?T-R?x.fillRect(--i+C(i*i*i*t)/5,t*240,T=R=(X+Y-T/2)/7,4):R-=h:T-R?T+=h:T=R+=h=.04)X=i/960*R-T+8,Y=t/4*R-T/2
```


# Be reserved

## Globals

| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 9 | const v=4 | let v=4 | 7 | 
| 7 | let v=4 | v=4 | 3 | 
| 7 | u=4,v=4 | u=v=4 | 5 | 


## Functionally

| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 17 | function F(j,f){} | F=(j,f)=>{} | 11 | 


```
F=(u,v)=>x.fillRect(u,v,8,8)

F(8,16)
F(16,16)
F(24,16)
```

```
F=(u,v)=>x.fillRect(u,v,8,8)||F

F(8,16)(16,16)(24,16)
```

```
F=(u,v)=>x.fillRect(u,v,8,8);F(8,16);F(16,16);F(24,16)
F=(u,v)=>x.fillRect(u,v,8,8)||F;F(8,16)(16,16)(24,16)
```

## Example

Title: **Circle Around**

Creator: **@KilledByAPixel**

URL: https://www.dwitter.net/d/33556

```
x.beginPath(x.fill(x.arc(960,540,6e3,t,t+3)))
```

##  For a while
| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 8 | while(1) | for(;;) | 7 |
| 38 | for(y=0;y<200;++y)for(x=0;x<320;++x){} | for(p=0;p<64000;++p){x=p%320;y=p/320} | 37 | 
| 37 | for(p=0;p<64000;++p){x=p%320;y=p/320} | for(p=64000;--p;){x=p%320;y=p/320} | 34 | 
| 34 | for(p=64000;--p;){x=p%320;y=p/320} | for(p=7e4;--p;){x=p%320;y=p/320} | 32 | 

Q. Is 320 already in a variable?
Q. Pass p%320 directly to a draw function?


## Example

Title: **Mountainous**

Creator: **@KilledByAPixel**

URL: https://www.dwitter.net/d/34033

```
for(i=2e3;i--;x.fillRect(i,t*60,1,z/7+.5))for(z=0,j=9;--j;z+=F(Y=t*5/j-z+j,X=i/19/j)*(1-Y%1)+Y%1*F(Y+1))F=Y=>X%1*S(X^Y)+(1-X%1)*S(X-1^Y)
```




## If...

| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 14 | if(t==0){n=12} | if(t==0)n=12 | 12 | 
| 12 | if(t==0)n=12 | if(!t)n=12 | 10 | 
| 10 | if(!t)n=12 | t?0:n=12 | 8 | 

## Example

Title: **99 bottles of beer**

Creator: **@marquisdegeek**

URL: https://www.dwitter.net/d/33592

```
c.width|=p=(t/1%5)>>>0\nN=100-t/5>>>0\nP=e=>e+` bottle${e==1?'':'s'} of beer`\nx.scale(9,9+t%5)\nx.fillText(N<1?'':p<2?P(N)+(p?'':` on the wall`):p>3?P(N-1):p>2?`Pass it around`:'Take one down',9,9)
```
Bonus: it handles the correct pluralisation of '1', and ends neatly




##  Split happens

| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 32 | "alpha,bravo,charlie".split(",") | "alpha0bravo0charlie".split(0) | 30 | 
| 30 | "alpha0bravo0charlie".split(0) | ["alpha","bravo","charlie"] | 27 | 

Benefits on shorter strings

| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 25 | ["a","b","c","d","e","f"] | "a,b,c,d,e,f".split(",") | 24 | 
| 24 | "a,b,c,d,e,f".split(",") | "a0b0c0d0e0f".split(0) | 22 | 





# Evaluation engine

## Comma chameleon

| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 32 | for(p=7e4;--p;){x=p%320;y=p/320} | for(p=7e4;--p;)x=p%320,y=p/320 | 30 | 

! That for() started out as 38 characters
! ...and probably reduces to 27


## Arrays

| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 11 | new Array() | new Array | 9 | 
| 9 | new Array | [] | 2 | 


| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 11 | new Array() | new Array | 9 | 
| 9 | new Array | [] | 2 | 


| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 12 | A="123";A[1] | "123"[1] | 8 | 
| 9 | new Array | [] | 2 | 

| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 10 | x.fillRect | F=x.fillRect;F() | 16 | 
| 10 | x.fillRect | F='fillRect';x\[F\]() | 19 | 


| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 10 | a.length>3 | 3 in a | 6 |



# Floor and parseInt

| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 15 | Math.floor(1.2) | ~~1.2 | 5 |
| 15 | Math.floor(1.2) | 1.2\|0 | 5 |
| 15 | Math.floor(a/2) | a/2\|0 | 5 |
| 15 | Math.floor(a/2) | a>>1 | 4 |
| 13 | Math.round(a) | a+.5\|0 | 6 |
| 11 | parseInt(s) | s\|0 | 3 | 



| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 20 | if(v==1\|\|v==2\|\|v==3) |  ~[1,2,3].indexOf(v) | 19 |




# CPU cycles


| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 8 | Infinity | 1/0 | 3 | 
| 11 | isFinite(a) | 1/a | 3 | 
| 9 | undefined  | []._ | 4 | 
| 20 | if(x==7)x=0;else x=7 | x==7?x=0:x=7 | 12 | 
| 12 | x==7?x=0:x=7 | x=x==7?0:7 | 10 | 
| 10 | x=x==7?0:7 | x=7-x | 5 | 

! Only works if you know x is a 0 or 7 - no defensive coding needed here



# Precedence



# Imperfections

## Is it close enough?

| Size | Before | After | Size |
| ---- | ---- | ---- | ---- |
| 17 | Math.random()<0.5 | new Date()&1 | 12 |
| 12 | new Date()&1 | new Date&1 | 10 |
| 30 | Math.floor(Math.random()*1337) | new Date&1337 | 13 |

## Example

Title: Race track

Creator: **@marquisdegeek**

URL: https://www.dwitter.net/d/33440
```
for(F=255,L=8e4;U=L%F,V=L/F,L--;)P=F/(V-79),N=(U/F-.5)*P-.05*S(t)*P*P,N*=N,D=S(P+F*t+V/9)>0,T=V<92?23:N>4?12:N>2?48+15*D:N<.01&&!D?63:21,x.fillStyle=R(T*5,T%16*20,T%4*85),x.fillRect(U*9,V*3,9,3)
```


# Resources

* https://dwitter.net/ (find mine at https://dwitter.net/u/marquisdegeek)
* https://capjs.3d2k.com/
* https://www.reddit.com/r/tinycode/
* https://js1k.com/
* https://www.pouet.net/
* https://code.golf
