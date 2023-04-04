# Hospital-Calculator
This is a basic C# program to calculate hospital bills. Basically is a input calculator and each day is $350 dollars. 



using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace B_Glass_program.cs
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            // Read input values from the text boxes
            int days = int.Parse(daysTextBox.Text);
            double medication = double.Parse(medicationTextBox.Text);
            double surgery = double.Parse(surgeryTextBox.Text);
            double lab = double.Parse(labTextBox.Text);
            double rehab = double.Parse(rehabTextBox.Text);

            // Calculate and display total charges
            double stayCharges = CalcStayCharges(days);
            double miscCharges = CalcMiscCharges(medication, surgery, lab, rehab);
            double totalCharges = CalcTotalCharges(stayCharges, miscCharges);
            totalChargesLabel.Text = $"Total charges: ${totalCharges:F2}";
        }
        private double CalcStayCharges(int days) => 350 * days;

        private double CalcMiscCharges(double medication, double surgery, double lab, double rehab)
            => medication + surgery + lab + rehab;

        private double CalcTotalCharges(double stayCharges, double miscCharges)
            => stayCharges + miscCharges;

        private void Form1_Load(object sender, EventArgs e)
        {
        }

        private void label1_Click(object sender, EventArgs e)
        {

        }
    }
}


Just make the following Textboxes and labels. 
