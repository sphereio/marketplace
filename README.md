SPHERE.IO marketplace
=====================

This repository contains information on how to build and run a marketplace on top of SPHERE.IO
A marketplace is the combination of retailers in to one central place - the marketplace.

In the SPHERE.IO space this means to connect projects - many retailer projects into one marketplace project, which we call master project.

# Overview

TODO: picture and definitions

# Architecture

In general, the SPHERE.IO projects used to build a marketplace do not differ from any other projects, but there are 2 important concepts in order to establish connections between the retailer projects and the master one. These 2 concepts are channels and the variant mapping.

### Channels

Using channels allows you to define where information is coming from or should be communicated to. The most important role of a channel is `SupplyChannel`, which can be used on price and stock level to identifiy different sources. In terms of a marketplace one supply channel indicates with its `key` property the SPHERE.IO project key of one retailer the information is originating from.

Further, channels of role `OrderImport` and `OrderExport` allow you to define where an order made at the marketplace has to be distributed to.
SPHERE.IO allows you here different possible scenarios:
- A marketplace order is designated to only one retailer and thus can simply be forwarded to it.
- A marketplace order contains line items that must be fulfilled by different retailers. Here the order must be splitted and distributed to different retailers.

### Variant mapping

The core of a marketplace is to sell the same products from different suppliers. Therefore, it is crucial to know which retailer sells which products - and even fine graned - which variant of the product.
With SPHERE.IO's rich PIM that allows you to model any kind of custom attributes for products, it is a simple attribute that allows the connection between a variant in a retailer project and the corresponding once in the master project.

# Connectors

With the above describe mapping information of channels and skus, the following micro services will help you to keep the data between the different retailer projects and your master project in sync.

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
