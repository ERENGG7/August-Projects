# August-Projects
C# projects form August
using Microsoft.VisualBasic;
using System;
using System.ComponentModel;
using System.Diagnostics.CodeAnalysis;
using System.Threading.Channels;
using System.Linq;
using System.Numerics;
using System.Collections.Generic;
using System.Runtime.InteropServices;

namespace Cars
{
    class Program
    {

        static void Main(string[] args)
        {
            Queue<string> queue = new Queue<string>();
            int totalCarsPassed = 0;
            int n = int.Parse(Console.ReadLine());
            while (true)
            {
                string cmd = Console.ReadLine();
                if (cmd == "green")
                {
                    for (int i = 0; i < n; i++)
                    {
                        if (queue.Count > 0)
                        {
                            var car = queue.Dequeue();
                            Console.WriteLine($"{car} passed!");
                            totalCarsPassed++;
                        }
                    }
                }
                else if (cmd == "end")
                {
                    Console.WriteLine($"{totalCarsPassed} cars passed the crossroad");
                    break;
                }
                else
                {
                    queue.Enqueue(cmd);
                }
            }
        }

    }

}
