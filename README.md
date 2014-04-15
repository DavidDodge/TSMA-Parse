TSMA-Parse - Another TSM_Accounting to CSV conversion tool‏
==========
NOTE: I’ve updated the conversion tool to read files in the new TSM 2.0 Accounting format. The TSM App will eventually have this feature built in, but in the meantime I’ll keep updating this tool. The tool only extracts the AH transactions.

TSMAParse is a tool to parse a TSM_Accounting saved variables file and generate a comma delimited file with the extracted transactions. You can open the resulting CSV file in Excel.

To use the tool, extract the program to a folder and run TSMAParse.exe. The proper usage is:

TSMAParse [inputfile] [outputfile]

If you don’t specify any parameters, TSMAParse will open a Windows form to let you enter the input and output files.

You will find your TSM_Accounting saved variables in your World of Warcraft install folder, in the subfolder "WTF\Account\<AccountName>\SavedVariables\TradeSkillMaster_Accounting.lua"

Each line in the output file contains the following information: Faction/Realm, Character, Buyer/Seller, Action, Item ID, Item Name, Stack Size, Quantity, Date, Time, Amount per Item. The price is in copper. For example, in the following line Chel bought 160 Elementium Ore from Mickey on May 5th, at a price of 18400 copper (1g84s00c) per ore. TSM_Accounting seems to combine multiple transactions into a single entry.

Alliance - Medivh, Chel, Mickey, buy, 52185, Elementium Ore, 20, 160, 05/05/2012, 17:57:47, 18400

I used Proudmoore's python script as a starting point, which in turn is a rewrite of Aeyron's ruby library. The result is a .NET Windows console application (sorry Mac users).

The tool uses the Luainterface library for reading the saved variables file. The Luainterface project home is http://code.google.com/p/luainterface/ if you would prefer to download Lua.dll and LuaInterface.dll directly. LuaInterface has some dependencies on the VisualC++ runtime library. It’s likely that you already have the VisualC++ runtimes on your machine, but if not, the recommended way of deploying the dependencies is to install the redist from here.

If you have any problems running TSMAParse, or have any suggestions for improvements, please let me know.

Application:
TSMAParse 2.0.zip - updated 19Aug2013

Source (C#, compiled in Visual Studio 2010):
TSMAParse_Source 2.0.zip - updated 19Aug2013