# Google-Trends-Trading

Algorithmic trading on QuantConnect

## What is the QuantConnect system.

![123](https://github.com/QuantConnect/Lean/blob/master/Documentation/2-Overview-Detailed-New.png)

The Engine is broken into many modular pieces which can be extended without touching other files. The modules are configured in config.json as set "environments". Through these environments, you can control LEAN to operate in the mode required.

The most important plugins are:

Result Processing (IResultHandler)

Handle all messages from the algorithmic trading engine. Decide what should be sent, and where the messages should go. The result processing system can send messages to a local GUI, or the web interface.

Datafeed Sourcing (IDataFeed)

Connect and download the data required for the algorithmic trading engine. For backtesting this sources files from the disk, for live trading, it connects to a stream and generates the data objects.

Transaction Processing (ITransactionHandler)

Process new order requests; either using the fill models provided by the algorithm or with an actual brokerage. Send the processed orders back to the algorithm's portfolio to be filled.

Realtime Event Management (IRealtimeHandler)

Generate real-time events - such as the end of day events. Trigger callbacks to real-time event handlers. For backtesting, this is mocked-up a works on simulated time.

Algorithm State Setup (ISetupHandler)

Configure the algorithm cash, portfolio and data requested. Initialize all state parameters required.

These are all configurable from the config.json file in the Launcher Project.

This program needs to be copy over to quantconnect for backtesting to work. 
