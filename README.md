using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace AbacusForm
{
    public partial class Abacus : Form
    {
        string Number = null;   //聲明接收運算數值

        string Symbol = null;   //聲明接收運算符字符

        public Abacus()
        {
            InitializeComponent();
        }

        //按鍵1
        private void NumKey1_Click(object sender, EventArgs e)
        {
            Button btn = (Button)sender;
            tbTotal.Text += btn.Text;
        }

        //按鍵2
        private void NumKey2_Click(object sender, EventArgs e)
        {
            Button btn = (Button)sender;
            tbTotal.Text += btn.Text;
        }

        //按鍵3
        private void NumKey3_Click(object sender, EventArgs e)
        {
            Button btn = (Button)sender;
            tbTotal.Text += btn.Text;
        }

        //按鍵4
        private void NumKey4_Click(object sender, EventArgs e)
        {
            Button btn = (Button)sender;
            tbTotal.Text += btn.Text;
        }

        //按鍵5
        private void NumKey5_Click(object sender, EventArgs e)
        {
            Button btn = (Button)sender;
            tbTotal.Text += btn.Text;
        }

        //按鍵6
        private void NumKey6_Click(object sender, EventArgs e)
        {
            Button btn = (Button)sender;
            tbTotal.Text += btn.Text;
        }

        //按鍵7
        private void NumKey7_Click(object sender, EventArgs e)
        {
            Button btn = (Button)sender;
            tbTotal.Text += btn.Text;
        }

        //按鍵8
        private void NumKey8_Click(object sender, EventArgs e)
        {
            Button btn = (Button)sender;
            tbTotal.Text += btn.Text;
        }

        //按鍵9
        private void NumKey9_Click(object sender, EventArgs e)
        {
            Button btn = (Button)sender;
            tbTotal.Text += btn.Text;
        }

        //按鍵0
        private void NumKey0_Click(object sender, EventArgs e)
        {
            Button btn = (Button)sender;
            tbTotal.Text += btn.Text;
        }

        //按鍵.
        private void Dot_Click(object sender, EventArgs e)
        {
            Button btn = (Button)sender;
            tbTotal.Text += btn.Text;
        }


        //清除計算結果
        private void btnClear_Click(object sender, EventArgs e)
        {
            tbTotal.Text = "";
        }


        //加法
        private void btnAdd_Click(object sender, EventArgs e)
        {
            //先判斷是否無輸入
            if (CheckEmpty())
                return;
            Button add = sender as Button;
            Symbol = add.Text;
            Number = tbTotal.Text;
            tbTotal.Text = "";
        }

        //減法
        private void btnSub_Click(object sender, EventArgs e)
        {
            //先判斷是否無輸入
            if (CheckEmpty())
                return;
            Button Sub = sender as Button;
            Symbol = Sub.Text;
            Number = tbTotal.Text;
            tbTotal.Text = "";
        }

        //乘法
        private void btnMult_Click(object sender, EventArgs e)
        {
            //先判斷是否無輸入
            if (CheckEmpty())
                return;
            Button Mult = sender as Button;
            Symbol = Mult.Text;
            Number = tbTotal.Text;
            tbTotal.Text = "";
        }

        //除法
        private void btnDiv_Click(object sender, EventArgs e)
        {
            //先判斷是否無輸入
            if (CheckEmpty())
                return;
            Button Div = sender as Button;
            Symbol = Div.Text;
            Number = tbTotal.Text;
            tbTotal.Text = "";
        }

        //等於
        private void Equal_Click(object sender, EventArgs e)
        {
            try
            {
                double a = double.Parse(Number);
                double b = double.Parse(tbTotal.Text);
                double c = 0;

                // + - * /
                switch (Symbol)
                {
                    case "+": c = a + b; break;
                    case "-": c = a - b; break;
                    case "*": c = a * b; break;
                    case "/": c = a / b;
                        //如果除0，輸出無法除0
                        if (b == 0)
                        {
                            tbTotal.Text = "無法除0";
                            return;
                        }
                        break;
                }
                tbTotal.Text = c.ToString();

            }
            catch (Exception)
            {
                if (CheckEmpty())
                    return;
            }

        }

        //判斷是否有輸入
        private bool CheckEmpty()
        {
            if (tbTotal.Text == string.Empty)
            {
                tbTotal.Text = "輸入錯誤";
                return true;
            }
            return false;
        }

    }
}
