            using System;
            using System.Collections.Generic;
            using System.Linq;
            using System.Text;
            using System.Threading.Tasks;

            namespace Stackoverflow_post
            {
                public class Post
                {
                    private int voteCount { get; set; }
                    public string title { get; set; }
                    public string description { get; set; }
                    public DateTime dateCreation { get; set; }

                    public Post()
                    {
                        this.title = "PlaceHolder Title";
                        this.description = "PlaceHolder Description";
                        this.dateCreation = DateTime.Now;
                    }

                    public Post(string Title, string Description)
                    {
                        this.title = Title;
                        this.description = Description;
                        this.dateCreation = DateTime.Now;
                    }

                    public void Vote(string vote)
                    {
                        if (vote == "down") this.voteCount--;
                        else if (vote == "up") this.voteCount++;
                    }

                    public string ShowPost()
                    {
                        return this.title + "\t" + this.dateCreation + "\n" +
                            this.description + "\n" +
                            "Vote: " + this.voteCount;
                    }
                }
            }
