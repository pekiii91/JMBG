# JMBG
jmbgvalidacija
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace JMBGValidacija
{
    public partial class Form1 : Form
    {
        Boolean JMBG = true;
        Boolean kontrolnaCifra = true;
        string prviBroj;
        string drugiBroj;
        string treciBroj;
        string cetvrtiBroj;
        string petiBroj;
        string sestiBroj;
        string sedmiBroj;
        string osmiBroj;
        string devetiBroj;
        string desetiBroj;
        string jedanaestiBroj;
        string dvanaestiBroj;
        string trinaestiBroj;
        string dan;
        string mesec;
        string godinaRodjenja;
        string regijaRodjenja;
        string mestoRodjenja;
        string drzavaRodjenja;
        string jedinstveniBrojPol;


        public Form1()
        {
            InitializeComponent();
        }

        private void txtBox1_KeyPress(object sender, KeyPressEventArgs e)
        {

        }

        private void Form1_Load(object sender, EventArgs e)
        {

        }

        private void txtBox2_KeyPress(object sender, KeyPressEventArgs e)
        {

        }

        private void txtBox3_KeyPress(object sender, KeyPressEventArgs e)
        {
            if (!char.IsDigit(e.KeyChar) && !char.IsControl(e.KeyChar))
            {
                e.Handled = true;
            }
        }

        private void btnProvera_Click(object sender, EventArgs e)
        {
            //validacija JMBG
            if (txtBox3.Text == " ")
            {
                MessageBox.Show("Jmbg polje mora biti popunjeno");
                JMBG = false;
            }
            else if (txtBox3.Text.Length != 13)
            {
                MessageBox.Show("Jmbg mora imati 13 brojeva:");
                JMBG = false;
            }

            //podela cifara
            string jbmg = txtBox3.Text.ToString();
            char[] charArray = jbmg.ToCharArray();
            for (int i = 0; i < charArray.Length; i++)
            {
         
                prviBroj = (charArray[0].ToString());
                drugiBroj = (charArray[1].ToString());
                treciBroj = (charArray[2].ToString());
                cetvrtiBroj = (charArray[3].ToString());
                petiBroj = (charArray[4].ToString());
                sestiBroj = (charArray[5].ToString());
                sedmiBroj = (charArray[6].ToString());
                osmiBroj = (charArray[7].ToString());
                devetiBroj = (charArray[8].ToString());
                desetiBroj = (charArray[9].ToString());
                jedanaestiBroj = (charArray[10].ToString());
                dvanaestiBroj = (charArray[11].ToString());
                trinaestiBroj = (charArray[12].ToString());

                dan = prviBroj + drugiBroj;
                mesec = treciBroj + cetvrtiBroj;
                godinaRodjenja = petiBroj + sestiBroj + sedmiBroj;
                regijaRodjenja = osmiBroj + devetiBroj;
            
                jedinstveniBrojPol = desetiBroj + jedanaestiBroj + dvanaestiBroj;

            }
            //prebacivanje u string

            int dan1 = int.Parse(dan);
            int mesec1 = int.Parse(mesec);
            int godinaRodjenja1 = int.Parse(godinaRodjenja);
            int regijaRodjenja1 = int.Parse(regijaRodjenja);
            int jedinstveniBrojPol1 = int.Parse(jedinstveniBrojPol);

            //meseci i danu
            
            if (mesec1 >= 1 && mesec1 <= 12 && dan1 <= 31)
            {
                switch (mesec1)
                {
                    case 1:
                        mesec = "Januar";
                        if (dan1 > 31)
                        {
                            MessageBox.Show(mesec + "Ne može imati više od 31 dan");
                            JMBG = false;
                        }
                        break;
                    case 2:
                        mesec = "Februar";
                        if (godinaRodjenja1 % 4 == 0)
                        {
                            if (dan1 > 29)
                            {
                                MessageBox.Show(mesec + "Februar prestupne ne moze imati vise od 29 dana prestupne godine");
                                JMBG = false;
                            }
                        }
                        else if (godinaRodjenja1 % 4 != 0)
                        {
                            if (dan1 > 28)
                            {
                                MessageBox.Show(mesec + "Februr neprestupne ne moze imati vise od 28 dana");
                                JMBG = false;
                            }
                        }
                        break;
                    case 3:
                        mesec = "Mart";
                        if (dan1 > 31)
                        {
                            MessageBox.Show(mesec + "Ne može imati više od 31 dan");
                            JMBG = false;
                        }
                        break;
                    case 4:
                        mesec = "April";
                        if (dan1 > 30)
                        {
                            MessageBox.Show(mesec + "Ne može imati više od 30 dan");
                            JMBG = false;
                        }
                        break;
                    case 5:
                        mesec = "Maj";
                        if (dan1 > 31)
                        {
                            MessageBox.Show(mesec + "Ne može imati više od 31 dan");
                            JMBG = false;
                        }
                        break;
                    case 6:
                        mesec = "Jun";
                        if (dan1 > 30)
                        {
                            MessageBox.Show(mesec + "Ne može imati više od 30 dan");
                            JMBG = false;
                        }
                        break;
                    case 7:
                        mesec = "Jul";
                        if (dan1 > 31)
                        {
                            MessageBox.Show(mesec + "Ne može imati više od 31 dan");
                            JMBG = false;
                        }
                        break;
                    case 8:
                        mesec = "Avgust";
                        if (dan1 > 31)
                        {
                            MessageBox.Show(mesec + "Ne može imati više od 30 dan");
                            JMBG = false;
                        }
                        break;
                    case 9:
                        mesec = "Septembar";
                        if (dan1 > 31)
                        {
                            MessageBox.Show(mesec + "Ne može imati više od 31 dan");
                            JMBG = false;
                        }
                        break;
                    case 10:
                        mesec = "Oktobar";
                        if (dan1 > 31)
                        {
                            MessageBox.Show(mesec + "Ne može imati više od 30 dan");
                            JMBG = false;
                        }
                        break;
                    case 11:
                        mesec = "Novembar";
                        if (dan1 > 30)
                        {
                            MessageBox.Show(mesec + "Ne može imati više od 31 dan");
                            JMBG = false;
                        }
                        break;
                    case 12:
                        mesec = "Decembar";
                        if (dan1 > 31)
                        {
                            MessageBox.Show(mesec + "Ne može imati više od 30 dan");
                            JMBG = false;
                        }
                        break;
                }
            }
            else
            {
                MessageBox.Show("Pogresan mjesec ili datum");
                JMBG = false;
            }

            //region
            if (regijaRodjenja1 > 0 && regijaRodjenja1 < 10)
            {
                drzavaRodjenja = "Stranci bez državljanstva bivše SFRJ";
                switch (regijaRodjenja1)
                {
                    case 1:
                        mestoRodjenja = "stranci u BiH";
                        break;
                    case 2:
                        mestoRodjenja = "stranci u Crnoj Gori";
                        break;
                    case 3:
                        mestoRodjenja = "stranci u Hrvatskoj";
                        break;
                    case 4:
                        mestoRodjenja = "stranci u Makedoniji";
                        break;
                    case 5:
                        mestoRodjenja = "stranci u Sloveniji";
                        break;
                    case 7:
                        mestoRodjenja = "stranci u Srbiji (bez pokrajina)";
                        break;
                    case 8:
                        mestoRodjenja = "stranci u Vojvodini";
                        break;
                    case 9:
                        mestoRodjenja = "stranci na Kosovu i Metohiji";
                        break;
                    default:
                        mestoRodjenja = "Nije Poznato";
                        break;
                }
            }

            if (regijaRodjenja1 > 10 && regijaRodjenja1 <= 19)
            {
                drzavaRodjenja = "Bosna i Hercegodina";
                switch (regijaRodjenja1)
                {
                    case 10:
                        mestoRodjenja = "Banja Luka";
                        break;
                    case 11:
                        mestoRodjenja = "Bihac";
                        break;
                    case 12:
                        mestoRodjenja = "Doboj";
                        break;
                    case 13:
                        mestoRodjenja = "Gorazde";
                        break;
                    case 14:
                        mestoRodjenja = "Livno";
                        break;
                    case 15:
                        mestoRodjenja = "Mostar";
                        break;
                    case 16:
                        mestoRodjenja = "Prijedor";
                        break;
                    case 17:
                        mestoRodjenja = "Sarajevo";
                        break;
                    case 18:
                        mestoRodjenja = "Tuzla";
                        break;
                    case 19:
                        mestoRodjenja = "Zenica";
                        break;
                    default:
                        mestoRodjenja = "Nije Poznato";
                        break;
                }

            }
            else if (regijaRodjenja1 > 20 && regijaRodjenja1 < 30)
            {
                drzavaRodjenja = "Crna Gora";
                switch (regijaRodjenja1)
                {
                    case 21:
                        mestoRodjenja = "Podgorica";
                        break;
                    case 26:
                        mestoRodjenja = "Niksic";
                        break;
                    case 29:
                        mestoRodjenja = "Pljevlja, ";
                        break;
                    default:
                        mestoRodjenja = "Nije Poznato";
                        break;
                }
            }

            else if (regijaRodjenja1 >= 30 && regijaRodjenja1 < 40)
            {
                drzavaRodjenja = "Hrvatska";
                switch (regijaRodjenja1)
                {
                    case 30:
                        mestoRodjenja = "Osijek, Slavonija region";
                        break;
                    case 31:
                        mestoRodjenja = "Bjelovar, Virovitica, Koprivnica, Pakrac, Podravina regija";
                        break;
                    case 32:
                        mestoRodjenja = "Varaždin, Medimurje regija";
                        break;
                    case 33:
                        mestoRodjenja = "Zagreb";
                        break;
                    case 34:
                        mestoRodjenja = "Karlovac";
                        break;
                    case 35:
                        mestoRodjenja = "Gospic, Lika regija";
                        break;
                    case 36:
                        mestoRodjenja = "Rijeka, Pula, Istra i Primorje regija";
                        break;
                    case 37:
                        mestoRodjenja = "Sisak, Banovina regija";
                        break;
                    case 38:
                        mestoRodjenja = "Split, Zadar, Dubrovnik, Dalmacija regija";
                        break;
                    case 39:
                        mestoRodjenja = "Ostalo";
                        break;
                    default:
                        mestoRodjenja = "Nije Poznato";
                        break;
                }
            }

            else if (regijaRodjenja1 > 40 && regijaRodjenja1 < 50)
            {
                drzavaRodjenja = "Makedonija";
                switch (regijaRodjenja1)
                {
                    case 41:
                        mestoRodjenja = "Bitolj";
                        break;
                    case 42:
                        mestoRodjenja = "Kumanovo";
                        break;
                    case 43:
                        mestoRodjenja = "Ohrid";
                        break;
                    case 44:
                        mestoRodjenja = "Prilep";
                        break;
                    case 45:
                        mestoRodjenja = "Skoplje";
                        break;
                    case 46:
                        mestoRodjenja = "Strumica";
                        break;
                    case 47:
                        mestoRodjenja = "Tetovo";
                        break;
                    case 48:
                        mestoRodjenja = "Veles";
                        break;
                    case 49:
                        mestoRodjenja = "Stip";
                        break;
                    default:
                        mestoRodjenja = "Nije Poznato";
                        break;
                }
            }

            else if (regijaRodjenja1 >= 50 && regijaRodjenja1 < 60)
            {
                drzavaRodjenja = "Slovenija";
                mestoRodjenja = "Slovenija";
            }

            else if (regijaRodjenja1 > 70 && regijaRodjenja1 < 80)
            {
                drzavaRodjenja = "Srbija";
                switch (regijaRodjenja1)
                {
                    case 71:
                        mestoRodjenja = "Beograd regija";
                        break;
                    case 72:
                        mestoRodjenja = "Šumadija";
                        break;
                    case 73:
                        mestoRodjenja = "Niš";
                        break;
                    case 74:
                        mestoRodjenja = "Južna Morava";
                        break;
                    case 75:
                        mestoRodjenja = "Zajecar";
                        break;
                    case 76:
                        mestoRodjenja = "Podunavlje";
                        break;
                    case 77:
                        mestoRodjenja = "Podrinje i Kolubara";
                        break;
                    case 78:
                        mestoRodjenja = "Kraljevo";
                        break;
                    case 79:
                        mestoRodjenja = "Uzice";
                        break;
                    default:
                        mestoRodjenja = "Nije Poznato";
                        break;
                }
            }

            else if (regijaRodjenja1 >= 80 && regijaRodjenja1 < 90)
            {
                drzavaRodjenja = "Srbija";
                switch (regijaRodjenja1)
                {
                    case 80:
                        mestoRodjenja = "Novi Sad";
                        break;
                    case 81:
                        mestoRodjenja = "Sombor";
                        break;
                    case 82:
                        mestoRodjenja = "Subotica";
                        break;
                    case 85:
                        mestoRodjenja = "Zrenjanin";
                        break;
                    case 86:
                        mestoRodjenja = "Pancevo";
                        break;
                    case 87:
                        mestoRodjenja = "Kikinda";
                        break;
                    case 88:
                        mestoRodjenja = "Ruma";
                        break;
                    case 89:
                        mestoRodjenja = "Sremska Mitrovica";
                        break;
                    default:
                        mestoRodjenja = "Nije Poznato";
                        break;
                }
            }

            else if (regijaRodjenja1 > 90 && regijaRodjenja1 < 99)
            {
                drzavaRodjenja = "Srbija";
                switch (regijaRodjenja1)
                {
                    case 91:
                        mestoRodjenja = "Pristina";
                        break;
                    case 92:
                        mestoRodjenja = "Kosovksa Mitrovica";
                        break;
                    case 93:
                        mestoRodjenja = "Pec";
                        break;
                    case 94:
                        mestoRodjenja = "Djakovica";
                        break;
                    case 95:
                        mestoRodjenja = "Prizren";
                        break;
                    case 96:
                        mestoRodjenja = "Gnjilane";
                        break;
                    default:
                        mestoRodjenja = "Nije Poznato";
                        break;
                }
            }




            if (jedinstveniBrojPol1 >= 000 && jedinstveniBrojPol1 <= 499)
            {
                jedinstveniBrojPol = "muski";
            }
            else if (jedinstveniBrojPol1 >= 500 && jedinstveniBrojPol1 <= 999)
            {
                jedinstveniBrojPol = "zenski";
            }

            checkKontrolnaCifra(); //poziv metode

            if (JMBG && kontrolnaCifra)
            {
                label1.Text = txtBox1.Text;
                label2.Text = txtBox2.Text;
                label4.Text = dan;
                label5.Text = mesec;
                if (sestiBroj == "0")
                {
                    label6.Text = "2" + godinaRodjenja;
                }
                else
                {
                    label6.Text = "1" + godinaRodjenja;

                }

                label7.Text = drzavaRodjenja;
                label8.Text = mestoRodjenja;
                label9.Text = jedinstveniBrojPol;

            }
            else
            {
                MessageBox.Show("Neisravan jmbg");
            }

            Boolean checkKontrolnaCifra()
            {
                int tacnaCifra;
                int prvaCifra1 = int.Parse(prviBroj);
                int drugaCifra1 = int.Parse(drugiBroj);
                int trecaCifra1 = int.Parse(treciBroj);
                int cetvrtaCifra1 = int.Parse(cetvrtiBroj);
                int petaCifra1 = int.Parse(petiBroj);
                int sestaCifra1 = int.Parse(sestiBroj);
                int sedmaCifra1 = int.Parse(sedmiBroj);
                int osmaCifra1 = int.Parse(osmiBroj);
                int devetaCifra1 = int.Parse(devetiBroj);
                int desetaCifra1 = int.Parse(desetiBroj);
                int jedanaestaCifra1 = int.Parse(jedanaestiBroj);
                int dvanaestaCifra1 = int.Parse(dvanaestiBroj);
                int trinaestaCifra1 = int.Parse(trinaestiBroj);


                int L = int.Parse(trinaestiBroj);

                tacnaCifra = 11 - ((7 * (prvaCifra1 + sedmaCifra1) +
                    6 * (drugaCifra1 + osmaCifra1) +
                    5 * (trecaCifra1 + devetaCifra1) +
                    4 * (cetvrtaCifra1 + desetaCifra1) +
                    3 * (petaCifra1 + jedanaestaCifra1) +
                    2 * (sestaCifra1 + dvanaestaCifra1)) % 11);

                if (tacnaCifra <= 9)
                {
                    if (tacnaCifra != L)
                    {
                        JMBG = false;
                        kontrolnaCifra = false;
                    }
                    else if (tacnaCifra > 9)
                    {
                        if (tacnaCifra != L)
                        {
                            JMBG = false;
                            kontrolnaCifra = false;
                        }
                    }

                }
                return kontrolnaCifra;
            }
        }
        private void btnObrisi_Click(object sender, EventArgs e)
        {
            txtBox1.Text = String.Empty;
            txtBox2.Text = String.Empty;
            txtBox3.Text = String.Empty;
            label4.Text = String.Empty;
            label5.Text = String.Empty;
            label6.Text = String.Empty;
            label7.Text = String.Empty;
            label8.Text = String.Empty;
            label9.Text = String.Empty;
        }


        private void btnExit_Click(object sender, EventArgs e)
        {
            Close();
        }

        private void label1_Click(object sender, EventArgs e)
        {

        }

        private void label2_Click(object sender, EventArgs e)
        {

        }

        private void label3_Click(object sender, EventArgs e)
        {

        }

        private void label4_Click(object sender, EventArgs e)
        {

        }

        private void label5_Click(object sender, EventArgs e)
        {

        }

        private void label6_Click(object sender, EventArgs e)
        {

        }

        private void label7_Click(object sender, EventArgs e)
        {

        }

        private void label8_Click(object sender, EventArgs e)
        {

        }

        private void label9_Click(object sender, EventArgs e)
        {

        }
    }
}

