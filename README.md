# UcakBiletFiyatiHesaplama

import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        int mesafe,yas, yolculuktipi;
        double yasIndirimi,indirimliTutar,gidisDonus,toplamTutar;
        double tutar=0.10;
        
        Scanner input = new Scanner(System.in);

        System.out.println("Yaş Giriniz: ");
       yas = input.nextInt();

        System.out.println("Mesafe Giriniz: ");
       mesafe = input.nextInt();

        System.out.println("Yolculuk Tipi Giriniz: ");
        yolculuktipi = input.nextInt();

        tutar = tutar*mesafe;
        yasIndirimi= tutar * 0.10;
        indirimliTutar = tutar - yasIndirimi;
        gidisDonus = indirimliTutar*0.20;
        toplamTutar = (indirimliTutar-gidisDonus)*2;

        System.out.println(toplamTutar);

        if ((yas>0 && mesafe>0) && (yolculuktipi==1)) {
            if (yas < 12) {
                toplamTutar = toplamTutar / 2;
            } else if (yas >= 12 && yas < 24) {
                toplamTutar = toplamTutar * (0.9);
            } else if (yas > 65) {
                toplamTutar = toplamTutar * 0.7;
            }
        } else if ((yas>0 && mesafe>0) && (yolculuktipi==2)){
            if (yas < 12) {
                toplamTutar = toplamTutar / 2-(toplamTutar *0.1);
            } else if (yas >= 12 && yas < 24) {
                toplamTutar = toplamTutar * (0.9*0.2);
            } else if (yas > 65) {
                toplamTutar = toplamTutar * 0.7*(0.2);
            }
        }
        else{
            System.out.println("Hatalı Veri Girdiniz!");
        }
    }
}
