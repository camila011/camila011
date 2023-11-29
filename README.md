import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import android.view.View
import android.widget.Button
import android.widget.TextView
import kotlinx.android.synthetic.main.activity_main.*

class MainActivity : AppCompatActivity() {
    private var num1: Float = 0.0f
    private var num2: Float = 0.0f
    private var result: Float = 0.0f
    private var operator: String = ""

    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        val btns = arrayOf(btn0, btn1, btn2, btn3, btn4, btn5, btn6, btn7, btn8, btn9)
        val txtInput = findViewById<TextView>(R.id.txtInput)

        for (i in btns.indices) {
            btns[i].setOnClickListener {
                txtInput.append((i).toString())
            }
        }

        btnPlus.setOnClickListener {
            num1 = txtInput.text.toString().toFloat()
            txtInput.text = ""
            operator = "+"
        }

        btnMinus.setOnClickListener {
            num1 = txtInput.text.toString().toFloat()
            txtInput.text = ""
            operator = "-"
        }

        btnMultiply.setOnClickListener {
            num1 = txtInput.text.toString().toFloat()
            txtInput.text = ""
            operator = "*"
        }

        btnDivide.setOnClickListener {
            num1 = txtInput.text.toString().toFloat()
            txtInput.text = ""
            operator = "/"
        }

        btnEquals.setOnClickListener {
            num2 = txtInput.text.toString().toFloat()
            txtInput.text = ""
            when (operator) {
                "+" -> result = num1 + num2
                "-" -> result = num1 - num2
                "*" -> result = num1 * num2
                "/" -> result = num1 / num2
            }
            txtInput.text = result.toString()
        }

        btnClear.setOnClickListener {
            txtInput.text = ""
            num1 = 0.0f
            num2 = 0.0f
            result = 0.0f
        }
    }
}

<!---
camila011/camila011 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
