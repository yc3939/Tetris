# Tetris

This is a mini project about Embedded System

## Table of Contents

- [Background](#background)

- [Requirement](#requirement)

- [Functions](#functions)

- [Techniques](#techniques)

- [SourceCodes](#sourceCodes)

## Background

This is a mini project about Embedded System. In this project, the Tetris game can work as any other online Tetris games. 

In order to drive those modules, I discussed with He Wang and Enze Ma about communication methods (SPI) and some fundamental functions.

## Requirement

Tetris requires the following to execute:

Atmel Studio 7.0

Arduino UNO

8*8 LED matrix with MAX7219

Two LEDs

One 7-segment display

## Functions

void SPI_Init(void)//Initialize SPI

void SPI_Transmit(char cData)//SPI.tansfer

void writeMax7219(char reg,char data)//Write into the chip

void SrightInitial(int k)//Let the first block shift right

void SrightNext(int k)//Let following blocks shift right

void SleftInitial(int k)//Let the first block shift left

void SleftNext(int k)//Let the following blocks shift left

void clearInitial(int k)//Clear the buffer called Showbuffer

void clearNext(int k)//Clear Showbuffer and RolldownBuffer

void testClr(int k)  //Test, if one line is full, then clear it

void score(int k)//Count the score and display it on 7-segment

void testTouch(int k)  //If one touch another during following, stop

void lose(int k)//Stop the game

void begin()//The flash at the beginning

void Reflect(int k, int j)//Reflect the previous buffer into display buffer

void InitialRoll(int k,int t)  //The first block roll

void NextRoll(int k, int m)  //Next rolls

void turnInitial(int k,int t)//The first block roll down

void turnNext(int k, int m)//Other blocks roll down

int main(void)//main function

ISR (INT0_vect);//clear all the buffer and re-begin the game

## Techniques

The techniques used in this mini project are:

SPI, interrupt, binary, 7-segment, switch

## Source Code

#include <avr/interrupt.h>

#include <util/delay.h>

#include <time.h>

#include <stdio.h>

#include <stdlib.h>

#include <string.h>
