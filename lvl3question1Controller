package com.example.project2;

import javafx.animation.FadeTransition;
import javafx.fxml.FXML;
import javafx.fxml.FXMLLoader;
import javafx.fxml.Initializable;
import javafx.scene.control.Button;
import javafx.scene.layout.AnchorPane;
import javafx.util.Duration;

import java.io.IOException;
import java.net.URL;
import java.util.ResourceBundle;

public class lvl3question1Controller implements Initializable {
    @FXML
    AnchorPane root;//pane

    @FXML
    Button choice1;

    @FXML
    Button choice2;//right answer

    @FXML
    Button nextBtn;

    @Override
    public void initialize(URL url, ResourceBundle rb){
        //checks if the congrats screen has already been viewed , if yes: the program will not play it
        if(!main.isSplash)
            loadSplashScreen();
    }




    //when clicking next button the scene will change IF the user chose one of the options
    public void nextClicked(){
        AnchorPane game2pane;
        try {
            game2pane = FXMLLoader.load(getClass().getResource("lvl3question2.fxml"));
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
        root.getChildren().setAll(game2pane);

    }
    //these 2 methods makes the button green if the right answer has been chosen, red otherwise
    //also disables the other choice and enables the next button!
    public void choice1Clicked(){
        choice1.setId("wrongAnswer");
        choice2.setDisable(true);
        nextBtn.setDisable(false);
    }

    public void choice2Clicked(){
        choice2.setId("rightAnswer");
        choice1.setDisable(true);
        nextBtn.setDisable(false);

    }



    //congrats on reaching this final level
    public void loadSplashScreen(){
        try {
            main.isSplash=true;

            AnchorPane anchorpane = FXMLLoader.load(getClass().getResource("congratslvl3.fxml"));
            root.getChildren().setAll(anchorpane);
            FadeTransition fadeIn =  new FadeTransition(Duration.seconds(5),anchorpane);
            fadeIn.setFromValue(0);
            fadeIn.setToValue(1);
            fadeIn.setCycleCount(1);

            FadeTransition fadeOut =  new FadeTransition(Duration.seconds(3),anchorpane);
            fadeOut.setFromValue(1);
            fadeOut.setToValue(0);
            fadeOut.setCycleCount(1);

            fadeIn.play();

            fadeIn.setOnFinished(e->{
                fadeOut.play();
            });

            fadeOut.setOnFinished(e-> {
                try {
                    AnchorPane gamepane = FXMLLoader.load(getClass().getResource("lvl3question1.fxml"));
                    root.getChildren().setAll(gamepane);
                }
                catch (IOException ex) {
                    throw new RuntimeException(ex);
                }
            });


        } catch (IOException e) {
            throw new RuntimeException(e);
        }

    }



}
