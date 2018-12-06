package com.example.wilar.calculadora;

import android.os.Bundle;
import android.support.v7.app.AppCompatActivity;
import android.view.View;
import android.widget.TextView;

public class CalculadoraBasica extends AppCompatActivity {
    public TextView pant;
    public double operan1 , operan2, res;
    int ope;
    private View v;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_calculadora_basica);
        pant =(TextView) findViewById(R.id.txtcaja);
    }
    public void Boton1 (View v){
        this.v = v;
        String cap= pant.getText().toString();
        cap=cap+"1";
        pant.setText(cap);
    }

    public void Boton2(View v){
        String cap= pant.getText().toString();
        cap=cap+"2";
        pant.setText(cap);

    }
    public void Boton3 (View v){
        String cap= pant.getText().toString();
        cap=cap+"3";
        pant.setText(cap);

    }
    public void Boton4 (View v){
        String cap= pant.getText().toString();
        cap=cap+"4";
        pant.setText(cap);

    }
    public void Boton5 (View v){
        String cap= pant.getText().toString();
        cap=cap+"5";
        pant.setText(cap);

    }
    public void Boton6 (View v){
        String cap= pant.getText().toString();
        cap=cap+"6";
        pant.setText(cap);

    }
    public void Boton7(View v){
        String cap= pant.getText().toString();
        cap=cap+"7";
        pant.setText(cap);

    }
    public void Boton8 (View v){
        String cap= pant.getText().toString();
        cap=cap+"8";
        pant.setText(cap);
    }

    public void Boton9 (View v){
        String cap= pant.getText().toString();
        cap=cap+"9";
        pant.setText(cap);
    }

    public void Boton0 (View v){
        String cap= pant.getText().toString();
        cap=cap+"0";
        pant.setText(cap);

    }

    public void Botonpunt (View v){
        String cap=pant.getText().toString();
        cap=cap+".";
        pant.setText(cap);
    }



    public void Botonsum(View v){
        try{
            String aux1= pant.getText().toString();
            operan1= Double.parseDouble(aux1);
        }catch(NumberFormatException nfe){};
        pant.setText("");
        ope=1;
    }

    public void Botonres(View v){
        try{
            String aux1= pant.getText().toString();
            operan1= Double.parseDouble(aux1);
        }catch(NumberFormatException nfe){};
        pant.setText("");
        ope=2;
    }
    public void Botonmul (View v){
        try{
            String aux1= pant.getText().toString();
            operan1= Double.parseDouble(aux1);
        }catch(NumberFormatException nfe){}
        pant.setText("");
        ope=3;
    }

    public void Botondiv (View v){
        try{
            String aux1= pant.getText().toString();
            operan1= Double.parseDouble(aux1);
        }catch(NumberFormatException nfe){};
        pant.setText("");
        ope=4;
    }





    public void Botonigu (View v){
        try{
            String aux2= pant.getText().toString();
            operan2= Double.parseDouble(aux2);
        }catch(NumberFormatException nfe){};
        pant.setText("");

        if (ope==1){
            res=operan1+operan2;

        }else if (ope==2){
            res=operan1-operan2;

        }else if (ope==3){
            res=operan1*operan2;

        }else if (ope==4){
            if(operan2==0){
                pant.setText("Numero no se puede dividir para 0");
            }else{
                res= operan1/operan2;
            }

        }else if (ope==5){
            res=Math.pow(operan1, operan2);

        }else if (ope==6){
            res=operan2*(operan1/100.0);

        }else if (ope==7){
            res=Math.sqrt(operan1);

        }else if(ope==8){
            double rad=Math.toRadians(operan1);
            res= (Math.sin(rad));

        }else if(ope==9){
            double rad=Math.toRadians(operan1);
            res= (Math.cos(rad));

        }else if(ope==10){
            double rad=Math.toRadians(operan1);
            res= (Math.tan(rad));

        }else if(ope==11){
            double angulo = (Math.asin(operan1));
            res=Math.toDegrees(angulo);

        }else if(ope==12){
            double angulo = (Math.acos(operan1));
            res=Math.toDegrees(angulo);

        }else if(ope==13){
            double angulo = (Math.atan(operan1));
            res=Math.toDegrees(angulo);

        }else if (ope==14){
            res=1;
            for(double i=operan1; i>=1; i--){
                res=res*i;
            }
        }
        pant.setText(""+res);
        operan1=res;
    }

    public void Botonclear (View v){
        pant.setText("");
        operan1=0.0;
        operan2=0.0;
        res=0.0;
    }

    public void Botonborrar (View v){
        if (!pant.getText().toString().equals("")){
            pant.setText(pant.getText().subSequence(0,pant.getText().length()-1)+"");
        }
    }

    public void off (View v){
        finish();
    }
}
