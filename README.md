# YearMonthDate
Difference of the days between two years month and date
static void Main(string[] args)
        {
            task10();


            Console.ReadKey();
        }
        static void task10()
        {
            Console.WriteLine("Enter a year:");
            int year1 = Int32.Parse(Console.ReadLine());
            Console.WriteLine("Enter a month :");
            int month1 = Int32.Parse(Console.ReadLine());
            Console.WriteLine("Enter a date :");
            int date1 = Int32.Parse(Console.ReadLine());
            Console.WriteLine("Enter a year:");
            int year2 = Int32.Parse(Console.ReadLine());
            Console.WriteLine("Enter a month :");
            int month2 = Int32.Parse(Console.ReadLine());
            Console.WriteLine("Enter a date :");
            int date2 = Int32.Parse(Console.ReadLine());
            int daysEveryYear = 365;
            int count = 0;
            int daysOfLeapYear = 0;
            int daysBetweenYear1andYear2 = 1;
            int yearDifference = year2 - year1;
            if (yearDifference > 1)
            {   for(int i = year1+1; i < year2; i++)
                {
                    if (i % 4 == 0)
                    {
                        daysOfLeapYear = 366;
                        count++;
                    }
                    daysBetweenYear1andYear2 = ((yearDifference-1-count) * daysEveryYear)+count*daysOfLeapYear;
                }
                
            }
            int difference = countDays(year1, month1, date1);
            int daysInTotal = daysCount(year2, month2, date2);
            int soTotalDays=difference+daysInTotal;
            Console.WriteLine("Now the total days are " + soTotalDays);
            Console.WriteLine("Difference :" + difference);
            Console.WriteLine("Days between two years are : " + daysBetweenYear1andYear2);
            Console.WriteLine("Finally the total days are :" + (soTotalDays + daysBetweenYear1andYear2));
            Console.ReadKey();


        }
        static int countDays(int year, int month, int date)
        {
            int differenceDays = 0;
            int yearDays = 365;
            
            
                int[] monthDays = { 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };



                if (year % 4 == 0)
            {
                monthDays[1] = 29;
                yearDays = 366;

            }
                    


           int dayCount = 0;
           int totalDay = 0;
           for (int i = 0; i <= month - 2; i++)
           {
                dayCount = dayCount + monthDays[i];

           }
            totalDay = dayCount + date;
            differenceDays = yearDays - totalDay;
            Console.WriteLine("The difference of days are: "+differenceDays);
                

            
            return differenceDays;
        }
        static int daysCount(int year, int month, int date)
        {
            int[] monthDays = { 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };



            if (year % 4 == 0)
                monthDays[1] = 29;


            int daysCount = 0;
            int totalDay = 0;
            for (int i = 0; i <= month - 2; i++)
            {
                daysCount = daysCount + monthDays[i];

            }
            totalDay = daysCount + date;

            // Console.WriteLine(totalDay);
            return totalDay;

        }
