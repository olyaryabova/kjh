// See https://aka.ms/new-console-template for more information

while (true)
{
    Console.WriteLine("Выберите действие: 1. Добавить запись");
    Console.WriteLine("2. Найти номер по имени");
    Console.WriteLine("3. Вывести записи");
    Console.WriteLine("4. Выход");

    Dictionary<string, string> dict = new Dictionary<string, string>();

    string menu = Console.ReadLine();


    switch (menu)
    {
        case "1":
            Console.WriteLine("Введите номер телефона:");
            string num = Console.ReadLine();
            Console.WriteLine("Введите имя:");
            string name = Console.ReadLine();

            if (dict.ContainsKey(num))
            {
                Console.WriteLine("Запись с таким именем уже существует!");
            }
            else
            {
                dict.Add(num, name);
                Console.WriteLine("Запись добавлена");
            }
            break;


        case "2":
            Console.WriteLine("Введите имя:");
            string findName = Convert.ToString(Console.ReadLine());

            if (dict.ContainsKey(findName))
            {
                Console.WriteLine($"Номер телефона: {dict[findName]}");
            }
            else
            {
                Console.WriteLine("Записи с таким именем не существует!");
            }
            break;

        case "3":
            Console.WriteLine("Существующие записи:");

            foreach (KeyValuePair<string, string> entry in dict)
            {
                Console.WriteLine($"Имя: {entry.Key}, Номер: {entry.Value}");
            }
            break;

        case "4":
            return;

        default:
            Console.WriteLine("Неверный выбор. Попробуйте снова.");
            break;
    }

    Console.WriteLine();
}
