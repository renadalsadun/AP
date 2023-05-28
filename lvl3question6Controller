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

public class lvl3question6Controller implements Initializable {
    @FXML
    AnchorPane root;//pane

    @FXML
    Button choice1;//

    @FXML
    Button choice2;//right answer

    @FXML
    Button nextBtn;

    @Override
    public void initialize(URL url, ResourceBundle rb) {
        //checks if the congrats screen has already been viewed , if yes: the program will not play it

    }


    //when clicking next button the scene will change IF the user chose one of the options
    public void nextClicked() {
        AnchorPane game2pane;
        try {
            game2pane = FXMLLoader.load(getClass().getResource("lvl3question7.fxml"));
        } catch (IOException e) {
            throw new RuntimeException(e);
        }
        root.getChildren().setAll(game2pane);

    }

    //these 2 methods makes the button green if the right answer has been chosen, red otherwise
    //also disables the other choice and enables the next button!
    public void choice1Clicked() {
        choice1.setId("wrongAnswer");
        choice2.setDisable(true);
        nextBtn.setDisable(false);
    }

    public void choice2Clicked() {
        choice2.setId("rightAnswer");
        choice1.setDisable(true);
        nextBtn.setDisable(false);

    }
}
