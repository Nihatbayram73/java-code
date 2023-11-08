# java-code
code for java
import java.util.Scanner; // Scanner sınıfı ile kullanıcının bir girdi girmesini sağlamak için kullandık.
import java.util.Arrays; // arrays sınıfı ile dizilerde işlem yapmak iin kolaylık sağlamak için kullandık.
import java.util.Random; // Rastgele sayı üretmek için Random sınıfını kullandık

public class uclu_odev {
    public static void main(String[] args) {
        Scanner x = new Scanner(System.in);
        System.out.print("NOT GİRİNİZ : ");
        int y = x.nextInt(); // Kullanıcın bir tamsayı girmesini sağlamak için nexInt komutunu yazdık.
        not(y); // Metot olarak çağırıp ekrana yazamsını sağladık
        sayiTahmini(); //Metot olarak çağırıp ekrana yazamsını sağladık
        int[] dizi = new int[10]; // burada dizimizin ve kaç elemanlı olduğunu tanımladık

        dizi(dizi); // Metot olarak çağırıp ekrana yazamsını sağladık



    }

    public static void not(int a) {
        if (a >= 0 && a <= 29) { // Buarada a'nın 0 ile 29 sayılarının arasında olan bir değeri için 'F' harfine karşılık not almasını sağladık ('0' ve '29' dahil)
            System.out.println("NOTUNUZUN HARF KARŞILIĞI : 'F'");
        } else if (a > 29 && a <= 44) {  // Buarada a'nın 29 ile 44 sayılarının arasında olan bir değeri için 'E' harfine karşılık not almasını sağladık ('29' dahil değil  ve '44' dahil)
            System.out.println("NOTUNUZUN HARF KARŞILIĞI : 'E'");
        } else if (a > 44 && a <= 59) {  // Buarada a'nın 44 ile 59 sayılarının arasında olan bir değeri için 'D' harfine karşılık not almasını sağladık ('44' dahil değil  ve '59' dahil)
            System.out.println("NOTUNUZUN HARF KARŞILIĞI : 'D'");
        } else if (a > 59 && a <= 74) {  // Buarada a'nın 59 ile 74 sayılarının arasında olan bir değeri için 'C' harfine karşılık not almasını sağladık ('59' dahil değil  ve '74' dahil)
            System.out.println("NOTUNUZUN HARF KARŞILIĞI : 'C'");
        } else if (a > 74 && a <= 84) {   // Buarada a'nın 74 ile 84 sayılarının arasında olan bir değeri için 'B' harfine karşılık not almasını sağladık ('74' dahil değil  ve '84' dahil)
            System.out.println("NOTUNUZUN HARF KARŞILIĞI : 'B'");
        } else if (a > 84 && a <= 100) {   // Buarada a'nın 84 ile 100 sayılarının arasında olan bir değeri için 'A' harfine karşılık not almasını sağladık ('84' dahil değil  ve '100' dahil)
            System.out.println("NOTUNUZUN HARF KARŞILIĞI : 'A'");
        }

    }

    public static void dizi(int[] dizi) {
        Scanner scanner = new Scanner(System.in);

        for (int i = 0; i < dizi.length; i++) {   //döngünün sayısı dizinin uzunluğu kadar yaptık bunu da length komutu ile yaptık
            System.out.print("Sayı " + (i + 1) + " girin: "); // burada kaçıncı sayıyı bizden istediğini gösteriyor.i +1 dememizim sebebi döngü "0" ile başlayacağı için.
            dizi[i] = scanner.nextInt();
        }

        Arrays.sort(dizi); // burada dizideki elemanları küçükten büyüğe sıralıyoruz

        System.out.print("Sıralı Dizi: ");// Print kullanmamızın sebebi çıktıyı bir alt satıra koymayıp direk sıralı dizi diye bir başlık yapıp diziyi yanına yazmasını sağladık.
        for (int sayi : dizi) { // sayı dizisini dizideki her bir elemanla eşleştirdik
            System.out.print(sayi + " ");
        }
    }

    public static void sayiTahmini() {
        Random x = new Random();
        int rastgeleSayi = x.nextInt(31); // 0 ile 30 arasında rastgele bir sayı üretir
        int sayac = 0;
        Scanner scanner = new Scanner(System.in);

        System.out.println("SAYI TAHMİN OYUNU 🎮🎰");


        while (true) { // while true ile doğru değerin girilinceye kadar sonsuz bir döngüye soktuk.
            System.out.print("Tahmininizi giriniz: ");
            int sayı = scanner.nextInt();
            sayac++; // sayacla kaç deneme sonucu doğru sayıya ulaştığımızı öğrenmik için kullandık

            if (sayı < 0 || sayı > 30) { // girecek sayının || işareti ile  0'dan küçükse veya 30'dan büyükse bize uyarı vermesini sağladık
                System.out.println("Lütfen 0 ile 30 arasında bir sayı girin.");
            } else if (sayı < rastgeleSayi) { // kullanıcıya ipucu vermek niyetiyle sayı eğer bilgisayarın ürettiği sayıdan küçük veya büyükse bunu kullanıcıya söyler
                System.out.println("Daha büyük bir sayı girin.");
            } else if (sayı > rastgeleSayi) { // kullanıcıya ipucu vermek niyetiyle sayı eğer bilgisayarın ürettiği sayıdan küçük veya büyükse bunu kullanıcıya söyler
                System.out.println("Daha küçük bir sayı girin.");
            } else {
                System.out.println("HELAL OLSUN GARDAŞ " + sayac + " deneme sonucu doğru sayıyı buldun. Sayı: " + rastgeleSayi); // Sayı tahmin edildiği zaman sayının kaç deneme sonucunda bulunduğunu ve rastgele üretilen sayıyı ekrana yazmak için bu kodun yazdık.
                break; // break komutu ile döngüyü sonlandırıyotuz
            }
        }
    }
}
