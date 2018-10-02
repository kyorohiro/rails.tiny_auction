FORMAT: 1A
HOST: http://polls.apiblueprint.org/

# Tiny Auction 

Auction Service template.

# Support

- English Auction


# API

## Key [/api/v0/keys]

### Create Key [POST]
+ Request (application/json)
        {
            "api_key": "api key",
            "roll": "0=>none, 7=>master"
        }

+ Response 200 (application/json)
        {
            "key": "key"
        }

### Delete Key [Delete]
+ Request (application/json)
        {
            "api_key": "api key",
        }

+ Response 200 (application/json)
        {
            "key": "key"
        }


## Token [/api/v0/tokens]

### Create Token [POST]
+ Request (application/json)
        {
            "api_key": "api key",
        }

+ Response 200 (application/json)
        {
            "token": "Token"
        }

### Delete Token [Delete]
+ Request (application/json)
        {
            "token": "token",
        }

+ Response 200 (application/json)
        {
            "token": "token"
        }



## Auctions [/api/v0/auctions]

### List All Auctions [GET]

+ Request
    + Headers
        Token: "Your Token"

+ Response 200 (application/json)
    + Body
        {
            auctions: [
                {
                    "id": "Auction ID",
                    "name": "Auction Name",
                    "auctioneer_id": "Auctioneer id",
                    "bid_id": "Bid id",
                    "bidder_id": "Bidder id",
                    "bidded_price": "Bidded Price",
                    "start_price": "Start Price",
                    "buyout_price": "Buyout price",
                    "minimum_increment_of_bid": "minimum increment of bid",
                    "start_date": "auction's start date",
                    "end_date": "auction's end date",
                    "status": "0=>none, 1=>start, 2=>end, 3=>stop"
                }
            ]
        }


### Create Auction [POST]

+ Request (application/json)
    + Headers
        Token: "Your Token"

    + Body
        {
            "name": "Auction Name",
            "auctioneer_id": "Auctioneer id",
            "start_price": "Start Price",
            "buyout_price": "Buyout price",
            "minimum_increment_of_bid": "minimum increment of bid",
            "start_date": "auction's start date",
            "end_date": "auction's end date"
        }

+ Response 200 (application/json)
        {
            auctions: [
                {
                    "id": "Auction ID"
                }
            ]
        }


## Auction [/api/v0/auctions/{+auction_id}]

### Show Auction [GET]
+ Request
    + Headers
        Token: "Your Token"

+ Response 200 (application/json)
        {
            auction: {
                "id": "Auction ID",
                "name": "Auction Name",
                "auctioneer_id": "Auctioneer id",
                "bid_id": "Bid id",
                "bidder_id": "Bidder id",
                "bidded_price": "Bidded Price",
                "start_price": "Start Price",
                "buyout_price": "Buyout price",
                "minimum_increment_of_bid": "minimum increment of bid",
                "start_date": "auction's start date",
                "end_date": "auction's end date",
                "status": "0=>none, 1=>start, 2=>end, 3=>stop"
            }
        }

### Update Auction [POST]
+ Request (application/json)
    + Headers
        Token: "Your Token"

    + Body
        {
        }

+ Response 200 (application/json)
        {
            "name": "Auction Name",
            "auctioneer_id": "Auctioneer id",
            "start_price": "Start Price",
            "buyout_price": "Buyout price",
            "minimum_increment_of_bid": "minimum increment of bid",
            "start_date": "auction's start date",
            "end_date": "auction's end date",
            "status": "0=>none, 1=>start, 2=>end, 3=>stop"
        }


## Bid [/api/v0/auctions/bid]

### Request BID [POST]
+ Request (application/json)
    + Headers
        Token: "Your Token"

    + Body
        {
            "auctio_id": "Auctioneer id",
            "bidder_id": "Bidder id",
            "bidded_price": "Bidded Price",
        }
        
+ Response 200 (application/json)
        {
            "bidded_id": "success",
            "result": "1=>success, 2=>failed"
        }


### List All BID [GET]
+ Request (application/json)
    + Headers
        Token: "Your Token"

    + Body
        {
            "bid_id": "bided id"
            "auctio_id": "Auctioneer id",
            "bidder_id": "Bidder id",
            "start_date": "Bidded Price",
            "end_date": "Bidded Price",
        }
        
+ Response 200 (application/json)
        {
            bids : [
                {
                    "id": "bid id"
                    "auctio_id": "Auctioneer id",
                    "bidder_id": "Bidder id",
                    "bidded_price": "Bidded Price",
                }
            ]
        }






