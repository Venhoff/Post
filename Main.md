# Post
Proste ćwiczenie symulujące tworzenie postu na forum.

                using System;
                using System.Collections.Generic;
                using System.Linq;
                using System.Text;
                using System.Threading.Tasks;

                namespace Stackoverflow_post
                {
                    class Program
                    {
                        static void Main(string[] args)
                        {
                            Post post = new Post("test", "podtytuł");

                            Console.WriteLine("Wpisz 'up' lub 'down' by zagłosować. Wpisz 'show' by pokazać post i ilosć głosów. Aby zakończyć program wpisz exit.");
                            while (true)
                            {
                                Console.WriteLine("Podaj komendę: ");
                                var input = Console.ReadLine();

                                if (String.IsNullOrWhiteSpace(input))
                                    Console.WriteLine("Proszę podać poprawną komendę.");

                                if (input.ToLower() == "show")
                                    Console.WriteLine(post.ShowPost());
                                else if (input.ToLower() == "up" || input.ToLower() == "down")
                                    post.Vote(input);
                                else if (input.ToLower() == "exit")
                                    break;
                            }

                        }
                    }
                }
