using System;
using System.Windows.Forms;

namespace PoiskRaboti
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void searchButton_Click(object sender, EventArgs e)
        {
            // Пример данных о навыках и соответствующих вакансиях
            string skills = skillsTextBox.Text;
            string predictedJob = GetPredictedJob(skills);
            resultsListBox.Items.Add($"Рекомендуемая должность: {predictedJob}");
        }

        // Метод для предсказания работы на основе введенных навыков
        private string GetPredictedJob(string skills)
        {
            // Заглушка для простоты: простая проверка наличия ключевых слов
            if (skills.Contains("C#") || skills.Contains(".NET"))
            {
                return "Программист на C#";
            }
            else if (skills.Contains("Python") || skills.Contains("Machine Learning"))
            {
                return "Специалист по данным";
            }
            else
            {
                return "Не удалось найти подходящую вакансию";
            }
        }
    }
}
