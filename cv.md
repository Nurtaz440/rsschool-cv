
<html>
<head>
</head>
<body>
<h1 align="margin-left">CV</h1>
  <h2 align="margin-left">Contact Info: </h2>
    <p>
      Hello, I am Nurtaza Ayxo'jayev
    </p>
 
<ul>
	<li><p><a href="@nurtazdev">Telegram </a></p></li>
	<li><p><a href="linkedin.com/in/nurtaza-ayxojayev-2994681a9">Linkedln </a></p></li>
	<li><p><a href="Nurtaz440">Github</a></p></li>
</ul>
<p> 
    <h2 align="margin-left">Summary  </h2>
     <p>
     I have desire to learn Android Studio well and work as junior.I have got less knowledge with Android Studio,I will wont to go to internship in summer.It helps me to get more knowledge which i do not have.Juniors do not stop to leraning because They have more thing they don't know.Knowledge is leanguege which deaf can hear and blind can see!!
    </p>
  </p>
    <h2 align="margin-left"> Skills </h2>
    <p>
    I started learning Android Studio last year.I learned more thing from Youtobe channels.I learned Android Studio with java.I study TDTU at Tashkent,now I am 2nd course at university.We have C++,proteus,Compus,Web development and Java lessons,Furthemore I know less kowledge with it too.
    </p>
     <h2 align="margin-left">Code examples: </h2>
      <p>
     package mening.dasturim.tablelayout;

public class MainActivity extends AppCompatActivity {

    private EditText display;
    private ImageView imageView;

    @RequiresApi(api = Build.VERSION_CODES.LOLLIPOP)
    @Override
    protected void onCreate(@Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        display=findViewById(R.id.edit_view);
        imageView=findViewById(R.id.image_view);
        display.setShowSoftInputOnFocus(false);

        display.setOnClickListener(v -> {
            if(getString(R.string.display_text).equals(display.getText().toString())){
                display.setText("");
            }
        });

        imageView.setOnClickListener(v->{
            Intent intent =new Intent(MainActivity.this,MainActivity2.class);
            startActivity(intent);
        });
    }
    private void updateText(String strToAdd){
        String oldStr=display.getText().toString();
        int cursorPos=display.getSelectionStart();
        String leftStr=oldStr.substring(0,cursorPos);
        String rightStr=oldStr.substring(cursorPos);
        if(getString(R.string.display_text).equals(display.getText().toString())){
            display.setText(strToAdd);
        }else {
            display.setText(String.format("%s%s%s", leftStr, strToAdd, rightStr));
        }
        display.setSelection(cursorPos + 1);
    }
    public void zeroBtn(@NonNull View view){
        updateText("0");
    }
    public void oneBtn(@NonNull View view){
        updateText("1");
    }
    public void twoBtn(@NonNull View view){
        updateText("2");
    }
    public void threeBtn(@NonNull View view){
        updateText("3");
    }
       public void fouroBtn(@NonNull View view){
        updateText("4");
    }
       public void fiveBtn(@NonNull View view){
        updateText("5");
    }
       public void sevenBtn(@NonNull View view){
        updateText("7");
    }
       public void eightBtn(@NonNull View view){
        updateText("8");
    }
       public void nineBtn(@NonNull View view){
        updateText("9");
    }
       public void sixBtn(@NonNull View view){
        updateText("6");
    }
       public void clearBtn(@NonNull View view){
        display.setText("");
    }

 public void sinusBtn(@NonNull View view){
        updateText("sin()");


    }
    public void cosBtn(@NonNull View view){
        updateText("cos()");
    }
    public void tanBtn(@NonNull View view){
        updateText("tan()");
    }
    public void arcsinBtn(@NonNull View view){
        updateText("arcsin()");
    }
       public void arccosBtn(@NonNull View view){
        updateText("arccos()");
    }
       public void arctanBtn(@NonNull View view){
        updateText("arctan()");
    }
       public void logBtn(@NonNull View view){
        updateText("log()");
    }
       public void lnBtn(@NonNull View view){
        updateText("ln()");
    }
       public void squarerootBtn(@NonNull View view){
        updateText("sqrt()");
    }
       public void eBtn(@NonNull View view){
        updateText("e");
    }
       @SuppressLint("SetTextI18n")
       public void piBtn(@NonNull View view){
        display.setText("pi");
    }
      @SuppressLint("SetTextI18n")
      public void abstaractBtn(@NonNull View view){
        display.setText("abs()");
    }

       public void primeBtn(@NonNull View view){
        updateText("ispr()");
    }
       public void xsquareBtn(@NonNull View view){
        updateText("^(2)");
    }
       public void xnsquareBtn(@NonNull View view){
        display.setText("^())");
        parBtn(view);

    }



       public void parBtn(@NonNull View view){

        int cursorPos=display.getSelectionStart();
        int openPar=0;
        int close = 0;
        int textLen=display.getText().length();

        for(int i=0;i<cursorPos;i++){
            if(display.getText().toString().startsWith("(", i)){
                openPar +=1;

            }else if(display.getText().toString().startsWith(")", i)){
                close +=1;
            }
        }
        if(openPar==close || display.getText().toString().startsWith("(", textLen-1)){

            updateText("(");

        }else if (close <openPar || !display.getText().toString().startsWith("(", textLen-1)){
            updateText(")");

        }
           display.setSelection(cursorPos+1);
    }
       public void expBtn(@NonNull View view){
        updateText("^");
    }
       public void plusMinusBtn(@NonNull View view){
        updateText("-");
    }
       public void decimalBtn(@NonNull View view){
        updateText(".");
    }
       public void addBtn(@NonNull View view){
        updateText("+");
    }
       public void subtractBtn(@NonNull View view){
        updateText("-");
    }
       public void equalBtn(@NonNull View view){

           String userExpresion=display.getText().toString();
           userExpresion=userExpresion.replaceAll("÷","/");
           userExpresion=userExpresion.replaceAll("×","*");

           Expression expression=new Expression(userExpresion);

           String result=String.valueOf(expression.calculate());

           display.setText(result);
           display.setSelection(result.length());

       }
    public void multiplyBtn(@NonNull View view){
        updateText("×");
    }
     public void divideBtn(@NonNull View view){
        updateText("÷");
    }

       public void backspaceBtn(@NonNull View view){

        int cursorPos=display.getSelectionStart();
        int textLen =display.getText().length();

        if(cursorPos != 0 && textLen != 0 ) {
            SpannableStringBuilder selecton = (SpannableStringBuilder) display.getText();

            selecton.replace(cursorPos - 1, cursorPos, "");

            display.setText(selecton);
            display.setSelection(cursorPos - 1);
        }
           }
}
    </p>
      <h2 align="margin-left"> Experience  </h2>
      <p>
  
  <a href="https://www.youtube.com/channel/UC6zqCVhCqAC76PXZg_hMOow"> I have youtobe channel</a>
  </p>
        <h2 align="margin-left">  Education  </h2>
          <p>
  
  <a href="https://www.youtube.com/redirect?event=channel_banner&redir_token=QUFFLUhqbS1YdjlCS3JBOGxlNXExX2pNazNTVE1vMFl5UXxBQ3Jtc0trZkNsZDZHS240OTJINWNkbmdRczBwcDFoMjZRNHhYWk1mWUdQZlhDVkJhYmtwU0JHYm5FZTlGM25nd0J1QVUwUkhFY2UxT2RKc1QwWjVQYjNyLXVVQkFOQ0FfWTYzVkxWS1A2SzhnTVVnMXJieHB1TQ&q=https%3A%2F%2Fgithub.com%2FPractical-Coding3">I learn Android Studio from youtobe channels</a>
  </p>
         <h2 align="margin-left"> English </h2>
         <p>
  I know English lenguege as Intermedite
  </p>
  </body>
</html>
