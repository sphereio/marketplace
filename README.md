SPHERE.IO marketplace
=====================

This repository contains information on how to build and run a marketplace on top of SPHERE.IO

A marketplace is the combination of a list of retailers in to one central place - the marketplace
In the SPHERE.IO space this means to connect projects - many retailer projects into one master project, which is the marketplace project. In

# Overview

TODO: picture

# Architecture

### Channels

### Variant mapping

# Connectors

### Price Sync

[sphere-price-sync](https://github.com/sphereio/sphere-price-sync)

### Stock Sync

[sphere-stock-sync](https://github.com/hajoeichler/sphere-stock-sync)

### Order Distribution

[sphere-order-distribution](https://github.com/hajoeichler/sphere-order-distribution)

### State sync

[sphere-message-processing](https://github.com/sphereio/sphere-message-processing)

##### Order states

[sphere-order-state-sync](https://github.com/sphereio/sphere-order-state-sync/blob/master/bin/sphere-order-state-sync.js)

##### Deliveries and Returns

[sphere-delivery-and-return-sync.js](https://github.com/sphereio/sphere-order-state-sync/blob/master/bin/sphere-delivery-and-return-sync.js)

### Retailer management

##### Line item state and stock management

[sphere-order-processing.js](https://github.com/sphereio/sphere-order-state-sync/blob/master/bin/sphere-order-processing.js)

##### Email notification

TBD
