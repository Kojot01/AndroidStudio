# AndroidStudio
package com.example.admin.jpo2016;

import java.util.ArrayList;
import java.util.List;

public class GrafSkierowany {
    public int liczba_krawedzi;
    public int liczba_wierzcholkow;
    public List<DirectedEdge>[] Lista; //Lista sąsiednich wierzchołków

    public GrafSkierowany(int liczba_wierzcholkow){
        this.liczba_krawedzi=0;
        this.liczba_wierzcholkow=liczba_wierzcholkow;
        this.Lista = (List<DirectedEdge>[]) new List[liczba_wierzcholkow];
        for(int i=0; i<liczba_wierzcholkow; i++){
           Lista[i]= new ArrayList<DirectedEdge>();
        }
    }
    public int getliczbakrawedzi() {
        return liczba_krawedzi;
    }

    public int getliczbawierzcholkow() {
        return liczba_wierzcholkow;
    }
    public void dodaj_krawedz(DirectedEdge krawedz){
        Lista[krawedz.A()].add(krawedz);
        liczba_krawedzi++;
    }

    public Iterable<DirectedEdge> getLista(int liczba_wierzcholkow){
        return Lista[liczba_wierzcholkow];
    }


}
