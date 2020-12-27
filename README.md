/*  Архипов М.О ИУ6-76 Вариант F2
*/



# HomeWork

using System;
using System.Text.Json;
using System.Text.Json.Serialization;


public class Song
{
    public string title {get; set;}
    public int year {get; set;}
    public string[] genres {get; set;}
    public Artist[] artists {get; set;}

  /*  public Song(string title, int year, string[] genres, Artist[] artists=null) {
        this.title = title;
        this.year = year;
        this.genres = genres;
        this.artists = artists;
    }
    */
}


public class Album
{
    public string title {get; set;}
    public int year {get; set;}
    public Song[] songs {get; set;}
    
  /*  public Album(string title, int year, Song[] songs) {
        this.title = title;
        this.year = year;
        this.songs = songs;
    }
    */
}


public class Artist
{
    public string first_name {get; set;}
    public string last_name {get; set;}
    
  /*  public Artist(string first_name, string last_name) {
        this.first_name = first_name;
        this.last_name = last_name;
    }
    
    */
}

public class Program
{
    public static void Main(String[] args) 
    { 
        
        Artist ben = new Artist { 
            first_name = "Ben", 
            last_name = "Howard" 
            
        };
        
        Song oats = new Song { 
            title = "Oats on the water", 
            year = 2012, 
            genres = new string[] {"folk", "indie"}, 
            artists = new Artist[] {ben}
            
        };
        
        Album island = new Album {
            title = "The Burgh Island",
            year = 2012,
            songs = new Song[] {oats}
        };
        
        string json = JsonSerializer.Serialize<Song>(oats);
        Console.WriteLine(json);
    } 
}
