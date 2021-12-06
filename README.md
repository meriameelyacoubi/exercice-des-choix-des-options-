# exercice-des-choix-des-options-

using System;
using System.Collections.Generic;

namespace Option
{
    class MainClass
    {
        public static void Main(string[] args)
        {
            var etudiant = new List<etudiant>()  
            {
                //chaque étudiant fait sont choix de filière 
                new etudiant('A', new List<char>("LBR")),  
                new etudiant('B', new List<char>("RBL")),
                new etudiant('C', new List<char>("BLR")),
                new etudiant('D', new List<char>("BRL")),
                new etudiant('E', new List<char>("LBR")),
            };
            var option = new List<option>()
            {
                //chaque option est affecté à l'étudiant selon la note 
                new option('L', new List<char>("BECAD")),
                new option('B', new List<char>("DECAB")),
                new option('R', new List<char>("ECDAB")),
            };

              

            // Write the pairs to console
            for (int i = 0; i < option.Count; i++)
            {
                Console.WriteLine(option[i].Id + " : " + option[i].Affecter.Id + " " + etudiant.Count);
            }
        }
    }

    public class Person
    {
        public List<char> Choices { get; set; }
        public char Id { get; set; }

        public Person(char id, List<char> choices)
        {
            Id = id;
            Choices = choices;
        }
    }

    public class option : Person
    {
        public etudiant Affecter { get; set; }

        public option(char id, List<char> choices) : base(id, choices) { }
    }

    public class etudiant : Person
    {
        public HashSet<char> ChoicesTried { get; set; } = new HashSet<char>();
        public char? NextChoiceId
        {
            get
            {
                char? choiceId = null;

                for (int i = 0; i < Choices.Count; i++)
                {
                    if (!ChoicesTried.Contains(Choices[i]))
                    {
                        choiceId = Choices[i];
                        break;
                    }
                }
                return choiceId;
            }
        }
        public option Affecter { get; set; }

        public etudiant(char id, List<char> choices) : base(id, choices) { }

        public void NextChoiceTried()
        {
            ChoicesTried.Add((char)NextChoiceId);
        }
    }
}
