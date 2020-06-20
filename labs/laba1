using System;
using System.Collections.Generic;
using System.Numerics;

namespace Courses
{
    class Program
    {
        static void Main(string[] args)
        {
            bool forward = true;
            while (forward)
            {
                UI.ShowMainMenu();
                UI.Choice(out forward);
            }
        }

        private class Record
        {
            private string name;
            private string surename;
            private string patronymic;
            private string telephoneNumber;
            private string country;
            private DateTime dateOfBirth;
            private string organization;
            private string position;
            private string moreNote;

            public string Name 
            {
                get
                { return name; }
                set
                { name = value; }
            }
            public string Surename
            {
                get
                { return surename; }
                set
                { surename = value; }
            }
            public string Patronymic
            {
                get
                { return patronymic; }
                set
                { patronymic = value; }
            }
            public string TelephoneNumber
            {
                get
                { return telephoneNumber; }
                set
                {
                    telephoneNumber = value;
                }
            }
            public string Country
            {
                get
                { return country; }
                set
                { country = value; }
            }
            public string DateOfBirth
            {
                get
                { return dateOfBirth.ToString(); }
                set
                { dateOfBirth = Convert.ToDateTime(value); }
            }
            public string Organization
            {
                get
                { return organization; }
                set
                { organization = value; }
            }
            public string Position
            {
                get
                { return position; }
                set
                { position = value; }
            }
            public string MoreNote
            {
                get
                { return moreNote; }
                set
                { moreNote = value; }
            }

            public override string ToString()
            {
                return $"Имя: {name}; Фамилия: {surename}; Отчетсво: {patronymic};\n" +
                       $"Номер телефона: {telephoneNumber};\n" +
                       $"Страна прживания: {country}; Дата рождения: {dateOfBirth};\n" +
                       $"Организация: {organization}; Должность: {position};\n" +
                       $"Дополнительные заметки: {moreNote};";
            }

            public string Showshort()
            {
                return $"Имя: {name};\n" +
                       $"Фамилия: {surename};\n" +
                       $"Номер телефона: {telephoneNumber};";
            }
        }

        static class RecordList
        {
            static public Dictionary<int, Record> arr = new Dictionary<int, Record>();
            static int currentKey = 0;

            static public void AddNewRecord()
            {
                Record newRecord = new Record();

                Console.WriteLine("Введите имя: ");
                newRecord.Name = Console.ReadLine();

                Console.WriteLine("Введите фамилию: ");
                newRecord.Surename = Console.ReadLine();

                Console.WriteLine("Хотите ввести отчество? y/n");
                char a = char.Parse(Console.ReadLine());
                if (a == 'y')
                {
                    Console.WriteLine("Введите отчечтво: ");
                    newRecord.Patronymic = Console.ReadLine();
                }
                else
                {
                    Console.WriteLine();
                }

                Console.WriteLine("Введите страну: ");
                newRecord.Country = Console.ReadLine();

                bool isInt = true;
                do
                {
                    Console.WriteLine("Введите номер телефона: ");
                    string telephoneNumber = Console.ReadLine();
                    int res;
                    isInt = Int32.TryParse(telephoneNumber, out res);
                    if (isInt)
                    {
                        newRecord.TelephoneNumber = telephoneNumber;
                    }
                } while (!isInt);

                Console.WriteLine("Хотите ввести дату рождения? y/n");
                a = char.Parse(Console.ReadLine());
                if (a == 'y')
                {
                    Console.WriteLine("Введите дату рождения: ");
                    newRecord.DateOfBirth = Console.ReadLine();
                }
                else
                {
                    Console.WriteLine();
                }

                Console.WriteLine("Хотите ввести организацию? y/n");
                a = char.Parse(Console.ReadLine());
                if (a == 'y')
                {
                    Console.WriteLine("Введите организацию: ");
                    newRecord.Organization = Console.ReadLine();
                }
                else
                {
                    Console.WriteLine();
                }

                Console.WriteLine("Хотите ввести должность? y/n");
                a = char.Parse(Console.ReadLine());
                if (a == 'y')
                {
                    Console.WriteLine("Введите должность: ");
                    newRecord.Position = Console.ReadLine();
                }
                else
                {
                    Console.WriteLine();
                }

                Console.WriteLine("Хотите ввести прочие заметки? y/n");
                a = char.Parse(Console.ReadLine());
                if (a == 'y')
                {
                    Console.WriteLine("Введите прочие заметки: ");
                    newRecord.MoreNote = Console.ReadLine();
                }
                else
                {
                    Console.WriteLine();
                }

                arr.Add(currentKey++, newRecord);
            }

            static public void DeleteRecord()
            {
                Console.Write("Input index: ");
                int a = int.Parse(Console.ReadLine());
                arr.Remove(a);
                Console.WriteLine();
            }

            static public void ShowWholeDictionary()
            {
                foreach (KeyValuePair<int, Record> keyValue in arr)
                {
                    Console.WriteLine(keyValue.Key + ":");
                    Console.WriteLine(keyValue.Value.Showshort());
                }
            }

            static public void ShowOneRecord()
            {
                Console.Write("Input index: ");
                int number = int.Parse(Console.ReadLine());
                Console.WriteLine();
                Record outRecord = new Record();
                bool isAbleToGet  = arr.TryGetValue(number, out outRecord);
                if (isAbleToGet)
                {
                    Console.WriteLine(outRecord);
                }
                else
                {
                    Console.WriteLine("Вы ввели несуществующий индекс!");
                }
            }

            static public void ChangeRecord()
            {
                Console.Write("Input index: ");
                int number = int.Parse(Console.ReadLine());
                Console.WriteLine();
                Record outRecord = new Record();
                bool isAbleToGet = arr.TryGetValue(number, out outRecord);
                if (isAbleToGet)
                {
                    arr.Remove(number);
                    Record newRecord = new Record();

                    Console.WriteLine("Введите имя: ");
                    newRecord.Name = Console.ReadLine();

                    Console.WriteLine("Введите фамилию: ");
                    newRecord.Surename = Console.ReadLine();

                    Console.WriteLine("Хотите ввести отчество? y/n");
                    char a = char.Parse(Console.ReadLine());
                    if (a == 'y')
                    {
                        Console.WriteLine("Введите отчечтво: ");
                        newRecord.Patronymic = Console.ReadLine();
                    }
                    else
                    {
                        Console.WriteLine();
                    }

                    Console.WriteLine("Введите страну: ");
                    newRecord.Country = Console.ReadLine();

                    bool isInt = true;
                    do
                    {
                        Console.WriteLine("Введите номер телефона: ");
                        string telephoneNumber = Console.ReadLine();
                        int res;
                        isInt = Int32.TryParse(telephoneNumber, out res);
                        if (isInt)
                        {
                            newRecord.TelephoneNumber = telephoneNumber;
                        }
                    } while (!isInt);

                    Console.WriteLine("Хотите ввести дату рождения? y/n");
                    a = char.Parse(Console.ReadLine());
                    if (a == 'y')
                    {
                        Console.WriteLine("Введите дату рождения: ");
                        newRecord.DateOfBirth = Console.ReadLine();
                    }
                    else
                    {
                        Console.WriteLine();
                    }

                    Console.WriteLine("Хотите ввести организацию? y/n");
                    a = char.Parse(Console.ReadLine());
                    if (a == 'y')
                    {
                        Console.WriteLine("Введите организацию: ");
                        newRecord.Organization = Console.ReadLine();
                    }
                    else
                    {
                        Console.WriteLine();
                    }

                    Console.WriteLine("Хотите ввести должность? y/n");
                    a = char.Parse(Console.ReadLine());
                    if (a == 'y')
                    {
                        Console.WriteLine("Введите должность: ");
                        newRecord.Position = Console.ReadLine();
                    }
                    else
                    {
                        Console.WriteLine();
                    }

                    Console.WriteLine("Хотите ввести прочие заметки? y/n");
                    a = char.Parse(Console.ReadLine());
                    if (a == 'y')
                    {
                        Console.WriteLine("Введите прочие заметки: ");
                        newRecord.MoreNote = Console.ReadLine();
                    }
                    else
                    {
                        Console.WriteLine();
                    }

                    arr.Add(number, newRecord);
                }
                else
                {
                    Console.WriteLine("Вы ввели несуществующий индекс!");
                }
            }
        }

        static class UI
        {
            static bool cont = true;
            static public void Choice(out bool cont)
            {
                cont = true;
                int choiceNumber = int.Parse(Console.ReadLine());
                switch (choiceNumber)
                {
                    case 1:
                        RecordList.AddNewRecord();
                        break;

                    case 2:
                        RecordList.ChangeRecord();
                        break;

                    case 3:
                        RecordList.DeleteRecord();
                        break;

                    case 4:
                        RecordList.ShowOneRecord();
                        break;

                    case 5:
                        RecordList.ShowWholeDictionary();
                        break;

                    case 6:
                        cont = false;
                        break;

                    default:
                        break;
                }
            }

            static public void ShowMainMenu()
            {
                Console.WriteLine("--------------------------------------------------------------------------------------------------------");
                Console.WriteLine("1. Добавить новую запись.");
                Console.WriteLine("2. Редактировать созданную запись.");
                Console.WriteLine("3. Удалить созданную запись.");
                Console.WriteLine("4. Просмотреть созданную запись.");
                Console.WriteLine("5. Просмотреть все созданные записи.");
                Console.WriteLine("6. Выход");
                Console.WriteLine("--------------------------------------------------------------------------------------------------------");
            }
        }
    }
}
