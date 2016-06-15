# AndroidStudio

package com.example.admin.jpo2016;

public class DirectedEdge {
    public int A;
    public int B;
    public long waga;

    public DirectedEdge(int A, int B, int waga)
    {
        this.A=A;
        this.B=B;
        this.waga=waga;
    }
    public int A() {
        return A;
    }

    public int B() {
        return B;
    }

    public long getwaga() {
        return waga;
    }
    public String toString() {
        return String.format("%d->%d (%d) ", A, B, waga);
    }

}
