# AndroidStudio
package com.example.admin.jpo2016;

import java.net.InetSocketAddress;
import java.util.ArrayDeque;
import java.util.ArrayList;
import java.util.Deque;
import java.util.List;
import java.util.PriorityQueue;
import java.util.Queue;

public class Dijkstra {
    class DystansDoKrawedzi implements Comparable<DystansDoKrawedzi> {
        public final int krawedz;
        public  long dystans;

        public DystansDoKrawedzi(int krawedz, long dystans)
        {
            this.krawedz=krawedz;
            this.dystans=dystans;
        }
        public long getdystans() {
            return dystans;
        }

        public void setdystans(long dystans) {
            this.dystans = dystans;
        }

        public int getkrawedz() {
            return krawedz;
        }
        @Override
        public int hashCode(){
            final int prime = 31;
            int result=1;
            result = prime * result + getOuterType().hashCode();
            result = prime*result+ (int)(dystans^(dystans>>>32));
            result = prime*result+krawedz;
            return result;
        }
        @Override
        public boolean equals(Object obj){
            if(this == obj) return true;
            if(obj==null) return false;
            if (getClass() != obj.getClass())
                return false;
            DystansDoKrawedzi other = (DystansDoKrawedzi) obj;
            if (!getOuterType().equals(other.getOuterType()))
                return false;
            if (dystans != other.dystans)
                return false;
            if (krawedz != other.krawedz)
                return false;
            return true;
        }

        @Override
        public int compareTo(DystansDoKrawedzi parametr) {
            int cmp = new Long(dystans).compareTo(parametr.getdystans());
            if(cmp==0) return new Integer(krawedz).compareTo(parametr.getkrawedz());

            return 0;
        }

        private Dijkstra getOuterType() {
            return Dijkstra.this;
        }
    }

    public DirectedEdge[] krawedzDo;
    public Long[] dystansDo;

    public Queue<DystansDoKrawedzi> priorityQueue;
    public Dijkstra(GrafSkierowany graf, int A){
    krawedzDo= new DirectedEdge[graf.getliczbawierzcholkow()];
    dystansDo= new Long[graf.getliczbawierzcholkow()];
    priorityQueue=new PriorityQueue<DystansDoKrawedzi>(graf.getliczbawierzcholkow());

        for (int v=0; v<graf.getliczbawierzcholkow();v++){
            dystansDo[v]=Long.MAX_VALUE;
        }
    dystansDo[A]=0L;
    priorityQueue.offer(new DystansDoKrawedzi(A, 0L));
    while(!priorityQueue.isEmpty()){
        relax(graf, priorityQueue.poll().getkrawedz());
    }
    }
    private void relax(GrafSkierowany graf, int v){
        for (DirectedEdge edge : graf.getLista(v)){

            int w=edge.B();

            if(dystansDo[w]>dystansDo[v]+edge.getwaga()){
               dystansDo[w]=dystansDo[v]+edge.getwaga();
               krawedzDo[w]=edge;
               DystansDoKrawedzi dte=new DystansDoKrawedzi(w, dystansDo[w]);

               priorityQueue.remove(dte);
               priorityQueue.offer(dte);
            }
        }

    }

   public long getdystansDo(int v)
   {
       return dystansDo[v];
   }
   public boolean PosiadaSciezke(int v){
       return dystansDo[v]<Long.MAX_VALUE;
   }

   public Iterable<DirectedEdge> getSciezkeDo(int v){
     Deque<DirectedEdge> path=new ArrayDeque<DirectedEdge>();
     if(!PosiadaSciezke(v)) return path;
     for(DirectedEdge krawedz=krawedzDo[v]; krawedz!=null; krawedz=krawedzDo[krawedz.A()]){
         path.push(krawedz);
     }
       return path;
   }

}
