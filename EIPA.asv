nx=50;
ny=100;
G = sparse(nx*ny,nx*ny);

for i=1:nx
    for j=1:ny
        N=j+(i-1)*ny;   % Current Position
        %bottom
        if j==1
            G(N,N)=1;
        %top
        elseif j==ny 
            G(N,N)=1;
        %left
        elseif i==1
            G(N,N)=1;
        %right
        elseif(i==nx)
            G(N,N)=1;
        %middle
        else
            Nxm=j + (i-2)*ny;
            Nxp=j + i*ny;
            Nym=j-1 + (i-1)*ny;
            Nyp=j+1 + (i-1)*ny;
            
            if(i<20 && i>10 && j>10 && j<20)
                G(N,N) = -2;
            else
                G(N,N) = -4;
            end
            G(N,Nyp)=1;
            G(N,Nym)=1;
            G(N,Nxm)=1;
            G(N,Nxp)=1;
        end        
    end
end

figure(1);
spy(G);

[E,D]=eigs(G,9,'sm');

for t=1:9
    for i=1:nx
        for j=1:ny
            N=j+(i-1)*ny;
            z(j,i)=E(N,t);
        end
    end
    figure(2)
    surf(z);
    pause(0.3);
end
