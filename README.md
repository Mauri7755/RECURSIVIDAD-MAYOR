# RECURSIVIDAD-MAYOR
 class Program
    {

        static int NumeroMayor(int[] x, int n, int Mayor)
        {

            if (n == 0)
            {
                if (Mayor < x[n])
                {
                    return x[0];
                }
                else
                {
                    return Mayor;
                }
            }
            else
            {
                if (Mayor < x[n])
                {
                    return NumeroMayor(x, n - 1, x[n]);
                }
                else
                {
                    return NumeroMayor(x, n - 1, Mayor);

                }
            }
        }


        static void Main(string[] args)
        {

            Random rmd = new Random();
            int m = 0, i;
            Console.WriteLine("ingrese el tamaño del vector que quiera el usuario");
            m = int.Parse(Console.ReadLine());

            int[] vec = new int[m];
            for (i = 0; i < m; i++)
            {
                vec[i] = rmd.Next(0, 50);
                Console.WriteLine(vec[i]);
            }
            Console.WriteLine("el numero mayor es:" + NumeroMayor(vec, m - 1, vec[0]));
            Console.ReadKey();
        }
