# Deribit Data Scraper
A library that can be used to download the entire BTC and ETH option chain data on Deribit.

## Example
``` python
>>> import deribit_data as dm
>>> btc_data = dm.Options("BTC")


# Get realised historical volatility
>>> df = btc_data.get_hist_vol()
>>> df.tail()
date                    btc_hist_vol
2020-05-13 21:00:00     95.228999
2020-05-13 22:00:00     95.501434
2020-05-13 23:00:00     95.553333
2020-05-14 00:00:00     95.572422
2020-05-14 01:00:00     95.564853


'''
Retrieve all options prices and relevant statistics. Note this may take several
minutes to download. Set save_csv=True to store a copy of this data to your local machine

'''
>>> df = data.get_options_stats()
>>> df.columns
    Index(['expiration_timestamp', 'option_type', 'instrument_name', 'strike',
           'underlying_price', 'underlying_index', 'timestamp', 'stats', 'state',
           'settlement_price', 'open_interest', 'min_price', 'max_price',
           'mark_price', 'mark_iv', 'last_price', 'interest_rate',
           'instrument_name', 'index_price', 'greeks', 'estimated_delivery_price',
           'change_id', 'bids', 'bid_iv', 'best_bid_price', 'best_bid_amount',
           'best_ask_price', 'best_ask_amount', 'asks', 'ask_iv'],
            dtype='object')

>>> df[['instrument_name', 'last_price', 'mark_iv', 'open_interest']].head()
      instrument_name	    last_price  mark_iv     open_interest
    0	BTC-22MAY20-9250-P	 0.0460	     77.72	      138.8
    1	BTC-22MAY20-12000-C	 0.0050	     112.28     	110.6
    2	BTC-26JUN20-8000-C	 0.1825	     90.26	      771.0
    3	BTC-14MAY20-8875-C	 0.0410	     90.65	      24.7
    4	BTC-25SEP20-9000-P	 0.1770	     83.37	      266.9
