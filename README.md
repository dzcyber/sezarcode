# sezarcode

import java.util.Scanner;

public class sezar_şifreleme {

	public  static String encrypted(String a,int key) {
		String şifreli="";
		String alphabet="ABCDEFGHIJKLMNOPQRSTUVWXYZ";
		String cipher="";
		for(int i=key;i<26+key;i++) {
			cipher+=alphabet.charAt(i%26);
		}
		System.out.println(cipher);
		
		int uzunluk=a.length();
		for(int i=0;i<uzunluk;i++) {
			for(int j=0;j<26;j++) {
				if(a.charAt(i)==alphabet.charAt(j)) {
					şifreli+=alphabet.charAt((j+key)%26);
				}
			}
		}
		
		return şifreli.toString();
		
	}
	
	
	public static void main(String[] args) {
		
		
		
		Scanner sn=new Scanner(System.in);
		System.out.print("Bir yazı giriniz:");
		String a=sn.nextLine();
		System.out.print("\nKayma miktarını giriniz:");
		int ks=sn.nextInt();

		 String k=a.toUpperCase();//HEPSİNİ BÜYÜKHARF YAPMAK İÇİN
		System.out.println("\nGirdiğinizin şifrelenmiş hali:"+encrypted(k,ks));
		System.out.print("Şifrenin çözülmüş hali:"+decrypt(encrypt(k,ks),ks));
	}
	public static String decrypt(String encrypt,int key) {
		String cipher="";
		String sade="";
		String alphabet="ABCDEFGHIJKLMNOPQRSTUVWXYZ";
		for(int i=0;i<26;i++) {
		   cipher+= alphabet.charAt(i);
		}
			System.out.println(cipher);
			
		int uzunluk=encrypt.length();
		for(int i=0;i<uzunluk;i++) {
			for(int j=0;j<26;j++) {
				if(encrypt.charAt(i)==alphabet.charAt(j)) {
					sade+=alphabet.charAt((char)(j-key+26)%26);
					
					
				}
					
						
					}
				}
			
		
		return sade.toString();
	}
	}
