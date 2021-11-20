self.label1['text']='Music_Unaused'
             
     
                   

#pause
        def pausemusic():      
                global paused 
                paused=TRUE
                mixer.music.pause()
                self.label1['text']='Music_Paused'self.label1=Label(self.root,text='Now Let The Music Play..',font=22,bg='red',fg='white')
        self.label1.pack(side=BOTTOM, fill=X)

#for play
        def playmusic():
                try:
                        paused
                except NameError:
                        try:
                                mixer.music.load('m3.mp3')
                                mixer.music.play()
                                self.label1['text']='Music_Playing..'
                        except:
                                pass
                        else:
                                mixer.music.unpause()


        self.photo_P2=ImageTk.PhotoImage(file='pause.png')
        photo_P2=Button(self.root,image=self.photo_P2,bd=0,bg='pink',command=pausemusic).place(x=215, y=400)



        #stop
        def stopmusic():
                mixer.music.stop()
                self.label1['text']='Music_Stoped'

        self.photo_P3=ImageTk.PhotoImage(file='stop.png')
        photo_P3=Button(self.root,image=self.photo_P3,bd=0,bg='pink',command=stopmusic).place(x=300, y=400)


        self.scale=Scale(self.root,from_=0, to=100,bg='cyan',length=150,width=10)
        self.scale.place(x=445, y=195)

        


    

root=Tk()
obj=musicplayer(root)
root.mainloop()
