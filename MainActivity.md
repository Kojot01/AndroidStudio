package com.example.admin.jpo2016;

import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;


public class MainActivity extends AppCompatActivity {

    EditText Txt1;
    EditText Txt2;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Txt1=(EditText)findViewById(R.id.Text1);
        Txt2=(EditText)findViewById(R.id.Text2);
    }


    public void kliknieto(View v){
    String Wpisane1=Txt1.getText().toString();
    String Wpisane2=Txt2.getText().toString();
    int A, B;
        A=1;
        B=1;

        GrafSkierowany Opawskie = new GrafSkierowany(12);
        Opawskie.dodaj_krawedz(new DirectedEdge(1, 2, 7));
        Opawskie.dodaj_krawedz(new DirectedEdge(1, 4, 6));
        Opawskie.dodaj_krawedz(new DirectedEdge(2, 1, 5));
        Opawskie.dodaj_krawedz(new DirectedEdge(2, 3, 1));
        Opawskie.dodaj_krawedz(new DirectedEdge(3, 2, 1));
        Opawskie.dodaj_krawedz(new DirectedEdge(3, 4, 2));
        Opawskie.dodaj_krawedz(new DirectedEdge(3, 8, 3));
        Opawskie.dodaj_krawedz(new DirectedEdge(3, 9, 3));
        Opawskie.dodaj_krawedz(new DirectedEdge(4, 1, 5));
        Opawskie.dodaj_krawedz(new DirectedEdge(4, 3, 1));
        Opawskie.dodaj_krawedz(new DirectedEdge(4, 5, 5));
        Opawskie.dodaj_krawedz(new DirectedEdge(4, 6, 2));
        Opawskie.dodaj_krawedz(new DirectedEdge(4, 9, 2));
        Opawskie.dodaj_krawedz(new DirectedEdge(5, 4, 6));
        Opawskie.dodaj_krawedz(new DirectedEdge(5, 6, 6));
        Opawskie.dodaj_krawedz(new DirectedEdge(6, 4, 3));
        Opawskie.dodaj_krawedz(new DirectedEdge(6, 5, 5));
        Opawskie.dodaj_krawedz(new DirectedEdge(6, 7, 2));
        Opawskie.dodaj_krawedz(new DirectedEdge(7, 6, 3));
        Opawskie.dodaj_krawedz(new DirectedEdge(7, 8, 4));
        Opawskie.dodaj_krawedz(new DirectedEdge(7, 9, 3));
        Opawskie.dodaj_krawedz(new DirectedEdge(7, 10, 4));
        Opawskie.dodaj_krawedz(new DirectedEdge(8, 3, 2));
        Opawskie.dodaj_krawedz(new DirectedEdge(8, 7, 3));
        Opawskie.dodaj_krawedz(new DirectedEdge(8, 9, 1));
        Opawskie.dodaj_krawedz(new DirectedEdge(9, 3, 2));
        Opawskie.dodaj_krawedz(new DirectedEdge(9, 4, 2));
        Opawskie.dodaj_krawedz(new DirectedEdge(9, 7, 2));
        Opawskie.dodaj_krawedz(new DirectedEdge(9, 8, 1));
        Opawskie.dodaj_krawedz(new DirectedEdge(10, 7, 3));
        Opawskie.dodaj_krawedz(new DirectedEdge(10, 11, 5));
        Opawskie.dodaj_krawedz(new DirectedEdge(10, 12, 4));
        Opawskie.dodaj_krawedz(new DirectedEdge(11, 10, 7));
        Opawskie.dodaj_krawedz(new DirectedEdge(12, 10, 6));


        if(Wpisane1=="Laka Prudnicka"){A=1;}
        if(Wpisane1=="Dlugota"){A=2;}
        if(Wpisane1=="Debowiec"){A=3;}
        if(Wpisane1=="Kobylica"){A=4;}
        if(Wpisane1=="Prudnik"){A=5;}
        if(Wpisane1=="Wzgorze Klasztorne"){A=6;}
        if(Wpisane1=="Trzebina"){A=7;}
        if(Wpisane1=="Sepik"){A=8;}
        if(Wpisane1=="Zbylut"){A=9;}
        if(Wpisane1=="Lipowiec"){A=10;}
        if(Wpisane1=="Dytmarow"){A=11;}
        if(Wpisane1=="Krzyzakowice"){A=12;}

        if(Wpisane2=="Laka Prudnicka"){B=1;}
        if(Wpisane2=="Dlugota"){B=2;}
        if(Wpisane2=="Debowiec"){B=3;}
        if(Wpisane2=="Kobylica"){B=4;}
        if(Wpisane2=="Prudnik"){B=5;}
        if(Wpisane2=="Wzgorze Klasztorne"){B=6;}
        if(Wpisane2=="Trzebina"){B=7;}
        if(Wpisane2=="Sepik"){B=8;}
        if(Wpisane2=="Zbylut"){B=9;}
        if(Wpisane2=="Lipowiec"){B=10;}
        if(Wpisane2=="Dytmarow"){B=11;}
        if(Wpisane2=="Krzyzakowice"){B=12;}

        Dijkstra droga=new Dijkstra(Opawskie, A);
        TextView newtext1, newtext2, newtext3, newtext4, newtext5, newtext6, newtext7, newtext8, newtext9, newtext10, newtext11, newtext12;
        newtext1=(TextView) findViewById(R.id.textView);
        newtext2=(TextView) findViewById(R.id.textView2);
        newtext3=(TextView) findViewById(R.id.textView3);
        newtext4=(TextView) findViewById(R.id.textView4);
        newtext5=(TextView) findViewById(R.id.textView5);
        newtext6=(TextView) findViewById(R.id.textView6);
        newtext7=(TextView) findViewById(R.id.textView7);
        newtext8=(TextView) findViewById(R.id.textView8);
        newtext9=(TextView) findViewById(R.id.textView9);
        newtext10=(TextView) findViewById(R.id.textView10);
        newtext11=(TextView) findViewById(R.id.textView11);

        TextView tablica[] = new TextView[11];
        tablica[0]=newtext1;
        tablica[1]=newtext2;
        tablica[2]=newtext3;
        tablica[3]=newtext4;
        tablica[4]=newtext5;
        tablica[5]=newtext6;
        tablica[6]=newtext7;
        tablica[7]=newtext8;
        tablica[8]=newtext9;
        tablica[9]=newtext10;
        tablica[10]=newtext11;
        int i=0;
        for(int target=B; target<Opawskie.getliczbawierzcholkow(); target++) {
            if (droga.PosiadaSciezke(target)) {
                if(target==1)tablica[i].setText("Laka Prudnicka");
                if(target==2)tablica[i].setText("Dlugota");
                if(target==3)tablica[i].setText("Debowiec");
                if(target==4)tablica[i].setText("Kobylica");
                if(target==5)tablica[i].setText("Prudnik");
                if(target==6)tablica[i].setText("Wzgorze Klasztorne");
                if(target==7)tablica[i].setText("Trzebina");
                if(target==8)tablica[i].setText("Sepik");
                if(target==9)tablica[i].setText("Zbylut");
                if(target==10)tablica[i].setText("Lipowiec");
                if(target==11)tablica[i].setText("Dytmarow");
                if(target==12)tablica[i].setText("Krzyzakowice");
            }
            if (droga.PosiadaSciezke(target))
            {
                for (DirectedEdge edge : droga.getSciezkeDo(target))
                {

                    System.out.print(edge);
                }


            }
    }
}




}
