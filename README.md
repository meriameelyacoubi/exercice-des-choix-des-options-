# exercice-des-choix-des-options-

using System;
using System.Collections.Generic;

namespace ChoixOption
{
 class MainClass
    {
    public static void Main(string[] args)
        {
        var etudiant = new List<etudiant>()
            {
                new etudiant('A', new List<char>("LBR")),
                new etudiant('B', new List<char>("RBL")),
                new etudiant('C', new List<char>("BRL")),
                new etudiant('D', new List<char>("BRL")),
                new etudiant('E', new List<char>("RLB")),
            };
            var women = new List<Woman>()
            {
                new option('L', new List<char>("BECAD")),
                new option('B', new List<char>("DECAB")),
                new option('R', new List<char>("ECDAB")),
                
            };
        }
    }
}
 public class option 
    {
        public option(char id, List<char> choices) : base(id, choices) { }
    }
 public class etudiant
    {
    }
