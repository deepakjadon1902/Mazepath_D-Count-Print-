import java.util.Scanner;

public class Main {
    static int count = 0;

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int N1 = scanner.nextInt();
        int N2 = scanner.nextInt();
        move(N1, N2, 0, 0, "");
        System.out.println();
        System.out.println(count);
    }

    public static void move(int N1, int N2, int i, int j, String path) {
        if (i == N1 - 1 && j == N2 - 1) {
            count++;
            System.out.print(path + " ");
            return;
        }
        if (i < N1 - 1) {
            move(N1, N2, i + 1, j, path + "V");
        }
        if (j < N2 - 1) {
            move(N1, N2, i, j + 1, path + "H");
        }
        if (i < N1 - 1 && j < N2 - 1) {
            move(N1, N2, i + 1, j + 1, path + "D");
        }
    }
}
