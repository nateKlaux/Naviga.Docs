# Activation fee for one-time payments (NCS Circ)

## Overview

This guide explores activation fees for one-time payments in NCS Circ.

## Before you start
Make sure you meet the following pre-requisites before starting the how-to steps:

* Have NCS Circ 2018.5 or greater
* Have set up an adjustment code for your activation fee in the NCS Circ database

## Guide

### Step 1

Provide a Naviga PM with the activation fee code and amount so they can configure your Subscribe’s MG2 Control.

### Step 2

Set up the activation fee code and amount for one-time payments in Subscribe’s MG2 Control using these settings:

* `DTI.ActivationFeeCode`
* `DTI.ActivationFeeAmount`

The front-end application calls NCS Circ's customer service API and `GETS Single Payment Terms Info` to fetch the one-time payment options. Along with the payment options, the activation fee is displayed.

## CSR Portal

## Self Service

After entering the payment information and selecting **submit**, the API `POST` the payment through NCS Circ and passes the `adjustment code 1` and `adjustment fee1` as an activation fee code and amount in real-time.

> Notes: If the client uses both the donation and activation fee options for one-time payments, then:

* `Adjustment code 1` and `amount 1` of the circ API is used for the activation fee code and the amount.

* `Adjustment code 2` and `amount 2` of the circ API is used for the donation code and the donation amount.

If the NCS Circ API payment calls `Payment Amount = (Term) + (Donation) + (Fee)`, then the tip is not included in the total payment amount. Instead its sent in the tip field.
