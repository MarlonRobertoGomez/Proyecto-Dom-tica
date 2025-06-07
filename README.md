package com.example.ejemplo_domotica; 
 
import androidx.appcompat.app.AppCompatActivity; 
 
import android.os.Bundle; 
import android.view.View; 
import android.widget.ImageButton; 
 
public class MainActivity extends AppCompatActivity implements 
View.OnClickListener 
{ 
    //atributos 
    ImageButton foco_pp; 
    ImageButton enchufe_pp; 
 
    boolean estado1 = false; 
    boolean estado2 = false; 
 
 
    @Override 
    protected void onCreate(Bundle savedInstanceState) 
    { 
        super.onCreate(savedInstanceState); 
        setContentView(R.layout.activity_main); 
 
        //Aplicacion 
        variable_botones(); 
        botones_accion(); 
    } 
 
    private void variable_botones() 
    { 
        foco_pp = findViewById(R.id.boton_foco_pp); 
        enchufe_pp = findViewById(R.id.boton_enchufe_pp); 
    } 
 
    private void botones_accion() 
    { 
        foco_pp.setOnClickListener(this); 
        enchufe_pp.setOnClickListener(this); 
    } 
 
    //metodo para detectar cual boton fue presionado 
    @Override 
    public void onClick(View v) 
    { 
        if(v == foco_pp) 
        { 
            estado1=!estado1; 
            cambiar_imagenes(estado1, foco_pp, 1); 
        } 
 
        if(v == enchufe_pp) 
        { 
            estado2=!estado2; 
            cambiar_imagenes(estado2, enchufe_pp, 2); 
        } 

        private void cambiar_imagenes(boolean estado, ImageButton boton, int 
eventos) 
{ 
if(estado == true && eventos == 1) 
{ 
boton.setImageResource(R.drawable.on); 
} 
if(estado == false && eventos == 1) 
{ 
boton.setImageResource(R.drawable.off); 
} 
if(estado == true && eventos == 2) 
{ 
boton.setImageResource(R.drawable.ton); 
} 
if(estado == false && eventos == 2) 
{ 
boton.setImageResource(R.drawable.toff); 
} 
}
}
