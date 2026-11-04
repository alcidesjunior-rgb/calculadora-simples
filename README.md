# Sistema de Caixa de Mercado






using System;
class Program
{
    static void MostrarProdutos()
    {
        Console.WriteLine("\n====== MERCADINHO ======");
        Console.WriteLine("1 - Arroz // R$25,00");
        Console.WriteLine("2 - Feijão // R$10,00");
        Console.WriteLine("3 - Leite  // R$6,00");
        Console.WriteLine("4 - Refrigerante // R$8,00");
    }

    /
    {
        switch(codigo)
        {
            case 1: 
            return 25;
            case 2:
            return 10;
            case 3:
            return 6;
            case 4:
            return 8;
            default:
            return 0;
        }
    }

    
    static string ObterNome(int codigo)
    {
        switch(codigo)
        {
            case 1: 
            
            return "Arroz";
            case 2: 
            
            return "Feijão";
            case 3: 
            
            return "Leite";
            case 4: 
            
            return "Refrigerante";
            default: 
            
            return "Produto inválido";
        }
    }

    static double CalcularTotal(double preco, int quantidade)
    {
        return preco * quantidade;
    }
    static void Main()
    {
        double totalCompra = 0;

        int continuar = 1;

        while(continuar == 1)
        {
        
            MostrarProdutos();

            Console.Write("\nEscolha o produto: ");
            int codigo = Convert.ToInt32(Console.ReadLine());

            string nome = ObterNome(codigo);

            double preco = ObterPreco(codigo);

            Console.Write("Quantidade: ");
            int quantidade = Convert.ToInt32(Console.ReadLine());

            double totalItem = CalcularTotal(preco, quantidade);

            totalCompra += totalItem;

            Console.WriteLine();
            Console.WriteLine("Produto: " + nome);
            Console.WriteLine("Total do item: R$ " + totalItem);

            Console.WriteLine();
            Console.WriteLine("Deseja adicionar outro produto?");
            Console.WriteLine("1 - Sim");
            Console.WriteLine("2 - Finalizar compra");

            continuar = Convert.ToInt32(Console.ReadLine());
        }

        Console.WriteLine();
        Console.WriteLine("====== FORMAS DE PAGAMENTO ======");

        Console.WriteLine("1 - PIX");
        Console.WriteLine("2 - Cartão");
        Console.WriteLine("3 - Dinheiro");

        Console.Write("Escolha: ");

        int pagamento = Convert.ToInt32(Console.ReadLine());

        Console.WriteLine();
        Console.WriteLine("====== RESUMO ======");

        Console.WriteLine("Valor total da compra: R$ " + totalCompra);

        switch(pagamento)
        {
            case 1:
                Console.WriteLine("Pagamento via PIX");
                break;

            case 2:
                Console.WriteLine("Pagamento via Cartão");
                break;

            case 3:
                Console.WriteLine("Pagamento em Dinheiro");
                break;

            default:
                Console.WriteLine("Forma de pagamento inválida.");
                break;
        }

        Console.WriteLine("\nObrigado pela preferência!");
    }
}
 
}
 
