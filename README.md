using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Flowers
{
    class Flowers
    {
        static void Main(string[] args)
        {
            int chrysanthemums = int.Parse(Console.ReadLine());
            int roses = int.Parse(Console.ReadLine());
            int tulips = int.Parse(Console.ReadLine());
            string season = Console.ReadLine().ToLower();
            string bankholiday = Console.ReadLine().ToLower();

            int countFlowers = chrysanthemums + roses + tulips;
            decimal price = 0;

            if (bankholiday == "n")
            {
                if (season == "spring" || season == "summer")
                {
                    price = chrysanthemums * 2.00m +roses * 4.10m +tulips * 2.50m;
                    if (season == "winter" && roses >= 10)
                    {
                        price *= 0.90m;
                    }
                }
                else if (season == "winter" || season == "autumn")
                {
                    price = chrysanthemums * 3.75m + roses * 4.50m + tulips * 4.15m;
                    if (season == "winter" && roses >= 10)
                    {
                        price *= 0.90m;
                    }
                }
            }
            else if (bankholiday == "y")
            {
                if (season == "spring" || season == "summer")
                {
                    price = chrysanthemums * 2.00m + roses * 4.10m + tulips * 2.50m;
                    price *= 1.15m;
                    if (season == "spring" && tulips > 7)
                    {
                        price *= 0.95m;
                    }                   
                }
                else if (season == "winter" || season == "autumn")
                {
                    price = chrysanthemums * 3.75m + roses * 4.50m + tulips * 4.15m;
                    price *= 1.15m;
                    if (season == "winter" && roses >= 10)
                    {
                        price *= 0.90m;
                    }
                }
            }

            if (countFlowers > 20)
            {
                price *= 0.80m;                
            }
            price += 2;

            Console.WriteLine($"{price:f2}");
        }
    }
}
