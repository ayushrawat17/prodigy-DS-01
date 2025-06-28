# prodigy-DS-01
{
 "cells": [
  {
   "cell_type": "markdown",
   "id": "fc72f458-caeb-411f-8ef5-b3790c2b5a44",
   "metadata": {},
   "source": [
    "# Task 1"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "25aac069-c11e-4082-8be0-f9a0e7d782fe",
   "metadata": {},
   "source": [
    "## Importing necessary libraries"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 2,
   "id": "89438671-7e00-4a31-b1fc-27664a21f2af",
   "metadata": {},
   "outputs": [],
   "source": [
    "import pandas as pd\n",
    "import numpy as np\n",
    "import matplotlib.pyplot as plt\n",
    "import seaborn as sns"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "5eaa27c5-7b23-4f84-bf0c-b77242a62e12",
   "metadata": {},
   "source": [
    "## Reading CSV file"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "id": "835f4c72-eb2d-4e3e-a7e9-670219ffc9e0",
   "metadata": {},
   "outputs": [],
   "source": [
    "df=pd.read_csv(\"worldpopulationdata.csv\")"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "393794a5-d03c-4bc5-8a1d-34df0586feff",
   "metadata": {},
   "source": [
    "## Checking top 5 rows data\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 5,
   "id": "90c7ec63-aa60-4811-aa0b-c3c75a867dfe",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>Series Name</th>\n",
       "      <th>Series Code</th>\n",
       "      <th>Country Name</th>\n",
       "      <th>Country Code</th>\n",
       "      <th>2022</th>\n",
       "      <th>2021</th>\n",
       "      <th>2020</th>\n",
       "      <th>2019</th>\n",
       "      <th>2018</th>\n",
       "      <th>2017</th>\n",
       "      <th>...</th>\n",
       "      <th>2010</th>\n",
       "      <th>2009</th>\n",
       "      <th>2008</th>\n",
       "      <th>2007</th>\n",
       "      <th>2006</th>\n",
       "      <th>2005</th>\n",
       "      <th>2004</th>\n",
       "      <th>2003</th>\n",
       "      <th>2002</th>\n",
       "      <th>2001</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>Population, total</td>\n",
       "      <td>SP.POP.TOTL</td>\n",
       "      <td>Afghanistan</td>\n",
       "      <td>AFG</td>\n",
       "      <td>41128771.0</td>\n",
       "      <td>40099462.0</td>\n",
       "      <td>38972230.0</td>\n",
       "      <td>37769499.0</td>\n",
       "      <td>36686784.0</td>\n",
       "      <td>35643418.0</td>\n",
       "      <td>...</td>\n",
       "      <td>28189672.0</td>\n",
       "      <td>27385307.0</td>\n",
       "      <td>26427199.0</td>\n",
       "      <td>25903301.0</td>\n",
       "      <td>25442944.0</td>\n",
       "      <td>24411191.0</td>\n",
       "      <td>23553551.0</td>\n",
       "      <td>22645130.0</td>\n",
       "      <td>21000256.0</td>\n",
       "      <td>19688632.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>Population, total</td>\n",
       "      <td>SP.POP.TOTL</td>\n",
       "      <td>Albania</td>\n",
       "      <td>ALB</td>\n",
       "      <td>2775634.0</td>\n",
       "      <td>2811666.0</td>\n",
       "      <td>2837849.0</td>\n",
       "      <td>2854191.0</td>\n",
       "      <td>2866376.0</td>\n",
       "      <td>2873457.0</td>\n",
       "      <td>...</td>\n",
       "      <td>2913021.0</td>\n",
       "      <td>2927519.0</td>\n",
       "      <td>2947314.0</td>\n",
       "      <td>2970017.0</td>\n",
       "      <td>2992547.0</td>\n",
       "      <td>3011487.0</td>\n",
       "      <td>3026939.0</td>\n",
       "      <td>3039616.0</td>\n",
       "      <td>3051010.0</td>\n",
       "      <td>3060173.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>Population, total</td>\n",
       "      <td>SP.POP.TOTL</td>\n",
       "      <td>Algeria</td>\n",
       "      <td>DZA</td>\n",
       "      <td>44903225.0</td>\n",
       "      <td>44177969.0</td>\n",
       "      <td>43451666.0</td>\n",
       "      <td>42705368.0</td>\n",
       "      <td>41927007.0</td>\n",
       "      <td>41136546.0</td>\n",
       "      <td>...</td>\n",
       "      <td>35856344.0</td>\n",
       "      <td>35196037.0</td>\n",
       "      <td>34569592.0</td>\n",
       "      <td>33983827.0</td>\n",
       "      <td>33435080.0</td>\n",
       "      <td>32956690.0</td>\n",
       "      <td>32510186.0</td>\n",
       "      <td>32055883.0</td>\n",
       "      <td>31624696.0</td>\n",
       "      <td>31200985.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>Population, total</td>\n",
       "      <td>SP.POP.TOTL</td>\n",
       "      <td>American Samoa</td>\n",
       "      <td>ASM</td>\n",
       "      <td>44273.0</td>\n",
       "      <td>45035.0</td>\n",
       "      <td>46189.0</td>\n",
       "      <td>47321.0</td>\n",
       "      <td>48424.0</td>\n",
       "      <td>49463.0</td>\n",
       "      <td>...</td>\n",
       "      <td>54849.0</td>\n",
       "      <td>55366.0</td>\n",
       "      <td>55891.0</td>\n",
       "      <td>56383.0</td>\n",
       "      <td>56837.0</td>\n",
       "      <td>57254.0</td>\n",
       "      <td>57626.0</td>\n",
       "      <td>57941.0</td>\n",
       "      <td>58177.0</td>\n",
       "      <td>58324.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>Population, total</td>\n",
       "      <td>SP.POP.TOTL</td>\n",
       "      <td>Andorra</td>\n",
       "      <td>AND</td>\n",
       "      <td>79824.0</td>\n",
       "      <td>79034.0</td>\n",
       "      <td>77700.0</td>\n",
       "      <td>76343.0</td>\n",
       "      <td>75013.0</td>\n",
       "      <td>73837.0</td>\n",
       "      <td>...</td>\n",
       "      <td>71519.0</td>\n",
       "      <td>73852.0</td>\n",
       "      <td>76055.0</td>\n",
       "      <td>78168.0</td>\n",
       "      <td>80221.0</td>\n",
       "      <td>79826.0</td>\n",
       "      <td>76933.0</td>\n",
       "      <td>73907.0</td>\n",
       "      <td>70849.0</td>\n",
       "      <td>67820.0</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "<p>5 rows × 26 columns</p>\n",
       "</div>"
      ],
      "text/plain": [
       "         Series Name  Series Code    Country Name Country Code        2022  \\\n",
       "0  Population, total  SP.POP.TOTL     Afghanistan          AFG  41128771.0   \n",
       "1  Population, total  SP.POP.TOTL         Albania          ALB   2775634.0   \n",
       "2  Population, total  SP.POP.TOTL         Algeria          DZA  44903225.0   \n",
       "3  Population, total  SP.POP.TOTL  American Samoa          ASM     44273.0   \n",
       "4  Population, total  SP.POP.TOTL         Andorra          AND     79824.0   \n",
       "\n",
       "         2021        2020        2019        2018        2017  ...  \\\n",
       "0  40099462.0  38972230.0  37769499.0  36686784.0  35643418.0  ...   \n",
       "1   2811666.0   2837849.0   2854191.0   2866376.0   2873457.0  ...   \n",
       "2  44177969.0  43451666.0  42705368.0  41927007.0  41136546.0  ...   \n",
       "3     45035.0     46189.0     47321.0     48424.0     49463.0  ...   \n",
       "4     79034.0     77700.0     76343.0     75013.0     73837.0  ...   \n",
       "\n",
       "         2010        2009        2008        2007        2006        2005  \\\n",
       "0  28189672.0  27385307.0  26427199.0  25903301.0  25442944.0  24411191.0   \n",
       "1   2913021.0   2927519.0   2947314.0   2970017.0   2992547.0   3011487.0   \n",
       "2  35856344.0  35196037.0  34569592.0  33983827.0  33435080.0  32956690.0   \n",
       "3     54849.0     55366.0     55891.0     56383.0     56837.0     57254.0   \n",
       "4     71519.0     73852.0     76055.0     78168.0     80221.0     79826.0   \n",
       "\n",
       "         2004        2003        2002        2001  \n",
       "0  23553551.0  22645130.0  21000256.0  19688632.0  \n",
       "1   3026939.0   3039616.0   3051010.0   3060173.0  \n",
       "2  32510186.0  32055883.0  31624696.0  31200985.0  \n",
       "3     57626.0     57941.0     58177.0     58324.0  \n",
       "4     76933.0     73907.0     70849.0     67820.0  \n",
       "\n",
       "[5 rows x 26 columns]"
      ]
     },
     "execution_count": 5,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.head(5)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "365a70dd-7970-4d1b-985b-1ca02c4ef898",
   "metadata": {},
   "source": [
    "## Checking data from bottom"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 6,
   "id": "c7fd9971-f37d-48a7-88c3-08db2493b022",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>Series Name</th>\n",
       "      <th>Series Code</th>\n",
       "      <th>Country Name</th>\n",
       "      <th>Country Code</th>\n",
       "      <th>2022</th>\n",
       "      <th>2021</th>\n",
       "      <th>2020</th>\n",
       "      <th>2019</th>\n",
       "      <th>2018</th>\n",
       "      <th>2017</th>\n",
       "      <th>...</th>\n",
       "      <th>2010</th>\n",
       "      <th>2009</th>\n",
       "      <th>2008</th>\n",
       "      <th>2007</th>\n",
       "      <th>2006</th>\n",
       "      <th>2005</th>\n",
       "      <th>2004</th>\n",
       "      <th>2003</th>\n",
       "      <th>2002</th>\n",
       "      <th>2001</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>1080</th>\n",
       "      <td>Population, male (% of total population)</td>\n",
       "      <td>SP.POP.TOTL.MA.ZS</td>\n",
       "      <td>Virgin Islands (U.S.)</td>\n",
       "      <td>VIR</td>\n",
       "      <td>46.613382</td>\n",
       "      <td>46.764444</td>\n",
       "      <td>46.914637</td>\n",
       "      <td>47.057307</td>\n",
       "      <td>47.185912</td>\n",
       "      <td>47.314214</td>\n",
       "      <td>...</td>\n",
       "      <td>47.801059</td>\n",
       "      <td>47.834540</td>\n",
       "      <td>47.870063</td>\n",
       "      <td>47.877604</td>\n",
       "      <td>47.870702</td>\n",
       "      <td>47.852669</td>\n",
       "      <td>47.825150</td>\n",
       "      <td>47.789128</td>\n",
       "      <td>47.754932</td>\n",
       "      <td>47.725126</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1081</th>\n",
       "      <td>Population, male (% of total population)</td>\n",
       "      <td>SP.POP.TOTL.MA.ZS</td>\n",
       "      <td>West Bank and Gaza</td>\n",
       "      <td>PSE</td>\n",
       "      <td>49.893678</td>\n",
       "      <td>49.877839</td>\n",
       "      <td>49.858957</td>\n",
       "      <td>49.835542</td>\n",
       "      <td>49.811374</td>\n",
       "      <td>49.785969</td>\n",
       "      <td>...</td>\n",
       "      <td>49.876336</td>\n",
       "      <td>49.898677</td>\n",
       "      <td>49.921445</td>\n",
       "      <td>49.947631</td>\n",
       "      <td>49.983323</td>\n",
       "      <td>50.028649</td>\n",
       "      <td>50.089953</td>\n",
       "      <td>50.167544</td>\n",
       "      <td>50.248196</td>\n",
       "      <td>50.321633</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1082</th>\n",
       "      <td>Population, male (% of total population)</td>\n",
       "      <td>SP.POP.TOTL.MA.ZS</td>\n",
       "      <td>Yemen, Rep.</td>\n",
       "      <td>YEM</td>\n",
       "      <td>50.519031</td>\n",
       "      <td>50.538516</td>\n",
       "      <td>50.554317</td>\n",
       "      <td>50.571320</td>\n",
       "      <td>50.596614</td>\n",
       "      <td>50.616964</td>\n",
       "      <td>...</td>\n",
       "      <td>50.594170</td>\n",
       "      <td>50.582692</td>\n",
       "      <td>50.568876</td>\n",
       "      <td>50.553633</td>\n",
       "      <td>50.539012</td>\n",
       "      <td>50.522514</td>\n",
       "      <td>50.502720</td>\n",
       "      <td>50.481666</td>\n",
       "      <td>50.459941</td>\n",
       "      <td>50.437238</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1083</th>\n",
       "      <td>Population, male (% of total population)</td>\n",
       "      <td>SP.POP.TOTL.MA.ZS</td>\n",
       "      <td>Zambia</td>\n",
       "      <td>ZMB</td>\n",
       "      <td>49.344602</td>\n",
       "      <td>49.344951</td>\n",
       "      <td>49.338301</td>\n",
       "      <td>49.326233</td>\n",
       "      <td>49.309087</td>\n",
       "      <td>49.288400</td>\n",
       "      <td>...</td>\n",
       "      <td>49.056379</td>\n",
       "      <td>48.981404</td>\n",
       "      <td>48.888443</td>\n",
       "      <td>48.784780</td>\n",
       "      <td>48.676944</td>\n",
       "      <td>48.571398</td>\n",
       "      <td>48.476900</td>\n",
       "      <td>48.393634</td>\n",
       "      <td>48.313646</td>\n",
       "      <td>48.229968</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1084</th>\n",
       "      <td>Population, male (% of total population)</td>\n",
       "      <td>SP.POP.TOTL.MA.ZS</td>\n",
       "      <td>Zimbabwe</td>\n",
       "      <td>ZWE</td>\n",
       "      <td>47.214139</td>\n",
       "      <td>47.167153</td>\n",
       "      <td>47.130679</td>\n",
       "      <td>47.099796</td>\n",
       "      <td>47.076238</td>\n",
       "      <td>47.051613</td>\n",
       "      <td>...</td>\n",
       "      <td>46.995893</td>\n",
       "      <td>47.049546</td>\n",
       "      <td>47.106068</td>\n",
       "      <td>47.166435</td>\n",
       "      <td>47.190963</td>\n",
       "      <td>47.231433</td>\n",
       "      <td>47.324096</td>\n",
       "      <td>47.387633</td>\n",
       "      <td>47.428426</td>\n",
       "      <td>47.460469</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "<p>5 rows × 26 columns</p>\n",
       "</div>"
      ],
      "text/plain": [
       "                                   Series Name        Series Code  \\\n",
       "1080  Population, male (% of total population)  SP.POP.TOTL.MA.ZS   \n",
       "1081  Population, male (% of total population)  SP.POP.TOTL.MA.ZS   \n",
       "1082  Population, male (% of total population)  SP.POP.TOTL.MA.ZS   \n",
       "1083  Population, male (% of total population)  SP.POP.TOTL.MA.ZS   \n",
       "1084  Population, male (% of total population)  SP.POP.TOTL.MA.ZS   \n",
       "\n",
       "               Country Name Country Code       2022       2021       2020  \\\n",
       "1080  Virgin Islands (U.S.)          VIR  46.613382  46.764444  46.914637   \n",
       "1081     West Bank and Gaza          PSE  49.893678  49.877839  49.858957   \n",
       "1082            Yemen, Rep.          YEM  50.519031  50.538516  50.554317   \n",
       "1083                 Zambia          ZMB  49.344602  49.344951  49.338301   \n",
       "1084               Zimbabwe          ZWE  47.214139  47.167153  47.130679   \n",
       "\n",
       "           2019       2018       2017  ...       2010       2009       2008  \\\n",
       "1080  47.057307  47.185912  47.314214  ...  47.801059  47.834540  47.870063   \n",
       "1081  49.835542  49.811374  49.785969  ...  49.876336  49.898677  49.921445   \n",
       "1082  50.571320  50.596614  50.616964  ...  50.594170  50.582692  50.568876   \n",
       "1083  49.326233  49.309087  49.288400  ...  49.056379  48.981404  48.888443   \n",
       "1084  47.099796  47.076238  47.051613  ...  46.995893  47.049546  47.106068   \n",
       "\n",
       "           2007       2006       2005       2004       2003       2002  \\\n",
       "1080  47.877604  47.870702  47.852669  47.825150  47.789128  47.754932   \n",
       "1081  49.947631  49.983323  50.028649  50.089953  50.167544  50.248196   \n",
       "1082  50.553633  50.539012  50.522514  50.502720  50.481666  50.459941   \n",
       "1083  48.784780  48.676944  48.571398  48.476900  48.393634  48.313646   \n",
       "1084  47.166435  47.190963  47.231433  47.324096  47.387633  47.428426   \n",
       "\n",
       "           2001  \n",
       "1080  47.725126  \n",
       "1081  50.321633  \n",
       "1082  50.437238  \n",
       "1083  48.229968  \n",
       "1084  47.460469  \n",
       "\n",
       "[5 rows x 26 columns]"
      ]
     },
     "execution_count": 6,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.tail(5)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "d98dee73-dad9-4e3d-a4ea-c966ea68b26c",
   "metadata": {},
   "source": [
    "## Checking the columns of the dataset"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 7,
   "id": "540de57e-1274-40b0-9c20-d20e20b04fb5",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "Index(['Series Name', 'Series Code', 'Country Name', 'Country Code', '2022',\n",
       "       '2021', '2020', '2019', '2018', '2017', '2016', '2015', '2014', '2013',\n",
       "       '2012', '2011', '2010', '2009', '2008', '2007', '2006', '2005', '2004',\n",
       "       '2003', '2002', '2001'],\n",
       "      dtype='object')"
      ]
     },
     "execution_count": 7,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.columns"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "47cf7183-a7d5-4b5c-8f27-5d0d5daac481",
   "metadata": {},
   "source": [
    "## Some information about the dataset"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 8,
   "id": "d992a59d-b4b7-44a8-ba08-067e5570e70b",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "<class 'pandas.core.frame.DataFrame'>\n",
      "RangeIndex: 1085 entries, 0 to 1084\n",
      "Data columns (total 26 columns):\n",
      " #   Column        Non-Null Count  Dtype  \n",
      "---  ------        --------------  -----  \n",
      " 0   Series Name   1085 non-null   object \n",
      " 1   Series Code   1085 non-null   object \n",
      " 2   Country Name  1085 non-null   object \n",
      " 3   Country Code  1085 non-null   object \n",
      " 4   2022          1085 non-null   float64\n",
      " 5   2021          1085 non-null   float64\n",
      " 6   2020          1085 non-null   float64\n",
      " 7   2019          1085 non-null   float64\n",
      " 8   2018          1085 non-null   float64\n",
      " 9   2017          1085 non-null   float64\n",
      " 10  2016          1085 non-null   float64\n",
      " 11  2015          1085 non-null   float64\n",
      " 12  2014          1085 non-null   float64\n",
      " 13  2013          1085 non-null   float64\n",
      " 14  2012          1085 non-null   float64\n",
      " 15  2011          1085 non-null   float64\n",
      " 16  2010          1085 non-null   float64\n",
      " 17  2009          1085 non-null   float64\n",
      " 18  2008          1085 non-null   float64\n",
      " 19  2007          1085 non-null   float64\n",
      " 20  2006          1085 non-null   float64\n",
      " 21  2005          1085 non-null   float64\n",
      " 22  2004          1085 non-null   float64\n",
      " 23  2003          1085 non-null   float64\n",
      " 24  2002          1085 non-null   float64\n",
      " 25  2001          1085 non-null   float64\n",
      "dtypes: float64(22), object(4)\n",
      "memory usage: 220.5+ KB\n"
     ]
    }
   ],
   "source": [
    "df.info()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 9,
   "id": "c0c93098-7354-4d3e-9602-e9c29c5d04df",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>2022</th>\n",
       "      <th>2021</th>\n",
       "      <th>2020</th>\n",
       "      <th>2019</th>\n",
       "      <th>2018</th>\n",
       "      <th>2017</th>\n",
       "      <th>2016</th>\n",
       "      <th>2015</th>\n",
       "      <th>2014</th>\n",
       "      <th>2013</th>\n",
       "      <th>...</th>\n",
       "      <th>2010</th>\n",
       "      <th>2009</th>\n",
       "      <th>2008</th>\n",
       "      <th>2007</th>\n",
       "      <th>2006</th>\n",
       "      <th>2005</th>\n",
       "      <th>2004</th>\n",
       "      <th>2003</th>\n",
       "      <th>2002</th>\n",
       "      <th>2001</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>count</th>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>...</td>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>1.085000e+03</td>\n",
       "      <td>1.085000e+03</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>mean</th>\n",
       "      <td>1.461378e+07</td>\n",
       "      <td>1.449711e+07</td>\n",
       "      <td>1.437307e+07</td>\n",
       "      <td>1.422876e+07</td>\n",
       "      <td>1.407966e+07</td>\n",
       "      <td>1.392568e+07</td>\n",
       "      <td>1.376711e+07</td>\n",
       "      <td>1.360705e+07</td>\n",
       "      <td>1.344625e+07</td>\n",
       "      <td>1.328368e+07</td>\n",
       "      <td>...</td>\n",
       "      <td>1.280537e+07</td>\n",
       "      <td>1.265031e+07</td>\n",
       "      <td>1.249535e+07</td>\n",
       "      <td>1.234099e+07</td>\n",
       "      <td>1.218858e+07</td>\n",
       "      <td>1.203685e+07</td>\n",
       "      <td>1.188626e+07</td>\n",
       "      <td>1.173626e+07</td>\n",
       "      <td>1.158653e+07</td>\n",
       "      <td>1.143598e+07</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>std</th>\n",
       "      <td>7.832944e+07</td>\n",
       "      <td>7.801505e+07</td>\n",
       "      <td>7.763257e+07</td>\n",
       "      <td>7.712985e+07</td>\n",
       "      <td>7.657562e+07</td>\n",
       "      <td>7.596457e+07</td>\n",
       "      <td>7.528760e+07</td>\n",
       "      <td>7.461740e+07</td>\n",
       "      <td>7.394894e+07</td>\n",
       "      <td>7.325356e+07</td>\n",
       "      <td>...</td>\n",
       "      <td>7.113128e+07</td>\n",
       "      <td>7.047509e+07</td>\n",
       "      <td>6.982016e+07</td>\n",
       "      <td>6.915934e+07</td>\n",
       "      <td>6.849229e+07</td>\n",
       "      <td>6.780708e+07</td>\n",
       "      <td>6.710041e+07</td>\n",
       "      <td>6.638386e+07</td>\n",
       "      <td>6.565651e+07</td>\n",
       "      <td>6.490862e+07</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>min</th>\n",
       "      <td>2.749000e+01</td>\n",
       "      <td>2.732503e+01</td>\n",
       "      <td>2.735104e+01</td>\n",
       "      <td>2.676295e+01</td>\n",
       "      <td>2.573928e+01</td>\n",
       "      <td>2.508394e+01</td>\n",
       "      <td>2.464721e+01</td>\n",
       "      <td>2.474106e+01</td>\n",
       "      <td>2.540718e+01</td>\n",
       "      <td>2.594943e+01</td>\n",
       "      <td>...</td>\n",
       "      <td>2.425072e+01</td>\n",
       "      <td>2.339422e+01</td>\n",
       "      <td>2.356750e+01</td>\n",
       "      <td>2.520779e+01</td>\n",
       "      <td>2.831990e+01</td>\n",
       "      <td>3.096426e+01</td>\n",
       "      <td>3.129133e+01</td>\n",
       "      <td>3.137472e+01</td>\n",
       "      <td>3.146521e+01</td>\n",
       "      <td>3.156689e+01</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>25%</th>\n",
       "      <td>5.034029e+01</td>\n",
       "      <td>5.035172e+01</td>\n",
       "      <td>5.034171e+01</td>\n",
       "      <td>5.033040e+01</td>\n",
       "      <td>5.033917e+01</td>\n",
       "      <td>5.033041e+01</td>\n",
       "      <td>5.033966e+01</td>\n",
       "      <td>5.033554e+01</td>\n",
       "      <td>5.032504e+01</td>\n",
       "      <td>5.033767e+01</td>\n",
       "      <td>...</td>\n",
       "      <td>5.034833e+01</td>\n",
       "      <td>5.036836e+01</td>\n",
       "      <td>5.037388e+01</td>\n",
       "      <td>5.036880e+01</td>\n",
       "      <td>5.038085e+01</td>\n",
       "      <td>5.037186e+01</td>\n",
       "      <td>5.036210e+01</td>\n",
       "      <td>5.039432e+01</td>\n",
       "      <td>5.039371e+01</td>\n",
       "      <td>5.038254e+01</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>50%</th>\n",
       "      <td>1.465500e+05</td>\n",
       "      <td>1.463660e+05</td>\n",
       "      <td>1.461650e+05</td>\n",
       "      <td>1.459570e+05</td>\n",
       "      <td>1.457520e+05</td>\n",
       "      <td>1.441350e+05</td>\n",
       "      <td>1.406060e+05</td>\n",
       "      <td>1.371850e+05</td>\n",
       "      <td>1.349620e+05</td>\n",
       "      <td>1.328960e+05</td>\n",
       "      <td>...</td>\n",
       "      <td>1.263090e+05</td>\n",
       "      <td>1.244660e+05</td>\n",
       "      <td>1.228070e+05</td>\n",
       "      <td>1.209490e+05</td>\n",
       "      <td>1.190890e+05</td>\n",
       "      <td>1.171330e+05</td>\n",
       "      <td>1.152950e+05</td>\n",
       "      <td>1.136960e+05</td>\n",
       "      <td>1.134500e+05</td>\n",
       "      <td>1.136410e+05</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>75%</th>\n",
       "      <td>5.903468e+06</td>\n",
       "      <td>5.856733e+06</td>\n",
       "      <td>5.831404e+06</td>\n",
       "      <td>5.814422e+06</td>\n",
       "      <td>5.774185e+06</td>\n",
       "      <td>5.686999e+06</td>\n",
       "      <td>5.629265e+06</td>\n",
       "      <td>5.544490e+06</td>\n",
       "      <td>5.524552e+06</td>\n",
       "      <td>5.480089e+06</td>\n",
       "      <td>...</td>\n",
       "      <td>5.267970e+06</td>\n",
       "      <td>5.187356e+06</td>\n",
       "      <td>5.100083e+06</td>\n",
       "      <td>5.062560e+06</td>\n",
       "      <td>5.007301e+06</td>\n",
       "      <td>4.989584e+06</td>\n",
       "      <td>4.813244e+06</td>\n",
       "      <td>4.758988e+06</td>\n",
       "      <td>4.698968e+06</td>\n",
       "      <td>4.535518e+06</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>max</th>\n",
       "      <td>1.417173e+09</td>\n",
       "      <td>1.412360e+09</td>\n",
       "      <td>1.411100e+09</td>\n",
       "      <td>1.407745e+09</td>\n",
       "      <td>1.402760e+09</td>\n",
       "      <td>1.396215e+09</td>\n",
       "      <td>1.387790e+09</td>\n",
       "      <td>1.379860e+09</td>\n",
       "      <td>1.371860e+09</td>\n",
       "      <td>1.363240e+09</td>\n",
       "      <td>...</td>\n",
       "      <td>1.337705e+09</td>\n",
       "      <td>1.331260e+09</td>\n",
       "      <td>1.324655e+09</td>\n",
       "      <td>1.317885e+09</td>\n",
       "      <td>1.311020e+09</td>\n",
       "      <td>1.303720e+09</td>\n",
       "      <td>1.296075e+09</td>\n",
       "      <td>1.288400e+09</td>\n",
       "      <td>1.280400e+09</td>\n",
       "      <td>1.271850e+09</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "<p>8 rows × 22 columns</p>\n",
       "</div>"
      ],
      "text/plain": [
       "               2022          2021          2020          2019          2018  \\\n",
       "count  1.085000e+03  1.085000e+03  1.085000e+03  1.085000e+03  1.085000e+03   \n",
       "mean   1.461378e+07  1.449711e+07  1.437307e+07  1.422876e+07  1.407966e+07   \n",
       "std    7.832944e+07  7.801505e+07  7.763257e+07  7.712985e+07  7.657562e+07   \n",
       "min    2.749000e+01  2.732503e+01  2.735104e+01  2.676295e+01  2.573928e+01   \n",
       "25%    5.034029e+01  5.035172e+01  5.034171e+01  5.033040e+01  5.033917e+01   \n",
       "50%    1.465500e+05  1.463660e+05  1.461650e+05  1.459570e+05  1.457520e+05   \n",
       "75%    5.903468e+06  5.856733e+06  5.831404e+06  5.814422e+06  5.774185e+06   \n",
       "max    1.417173e+09  1.412360e+09  1.411100e+09  1.407745e+09  1.402760e+09   \n",
       "\n",
       "               2017          2016          2015          2014          2013  \\\n",
       "count  1.085000e+03  1.085000e+03  1.085000e+03  1.085000e+03  1.085000e+03   \n",
       "mean   1.392568e+07  1.376711e+07  1.360705e+07  1.344625e+07  1.328368e+07   \n",
       "std    7.596457e+07  7.528760e+07  7.461740e+07  7.394894e+07  7.325356e+07   \n",
       "min    2.508394e+01  2.464721e+01  2.474106e+01  2.540718e+01  2.594943e+01   \n",
       "25%    5.033041e+01  5.033966e+01  5.033554e+01  5.032504e+01  5.033767e+01   \n",
       "50%    1.441350e+05  1.406060e+05  1.371850e+05  1.349620e+05  1.328960e+05   \n",
       "75%    5.686999e+06  5.629265e+06  5.544490e+06  5.524552e+06  5.480089e+06   \n",
       "max    1.396215e+09  1.387790e+09  1.379860e+09  1.371860e+09  1.363240e+09   \n",
       "\n",
       "       ...          2010          2009          2008          2007  \\\n",
       "count  ...  1.085000e+03  1.085000e+03  1.085000e+03  1.085000e+03   \n",
       "mean   ...  1.280537e+07  1.265031e+07  1.249535e+07  1.234099e+07   \n",
       "std    ...  7.113128e+07  7.047509e+07  6.982016e+07  6.915934e+07   \n",
       "min    ...  2.425072e+01  2.339422e+01  2.356750e+01  2.520779e+01   \n",
       "25%    ...  5.034833e+01  5.036836e+01  5.037388e+01  5.036880e+01   \n",
       "50%    ...  1.263090e+05  1.244660e+05  1.228070e+05  1.209490e+05   \n",
       "75%    ...  5.267970e+06  5.187356e+06  5.100083e+06  5.062560e+06   \n",
       "max    ...  1.337705e+09  1.331260e+09  1.324655e+09  1.317885e+09   \n",
       "\n",
       "               2006          2005          2004          2003          2002  \\\n",
       "count  1.085000e+03  1.085000e+03  1.085000e+03  1.085000e+03  1.085000e+03   \n",
       "mean   1.218858e+07  1.203685e+07  1.188626e+07  1.173626e+07  1.158653e+07   \n",
       "std    6.849229e+07  6.780708e+07  6.710041e+07  6.638386e+07  6.565651e+07   \n",
       "min    2.831990e+01  3.096426e+01  3.129133e+01  3.137472e+01  3.146521e+01   \n",
       "25%    5.038085e+01  5.037186e+01  5.036210e+01  5.039432e+01  5.039371e+01   \n",
       "50%    1.190890e+05  1.171330e+05  1.152950e+05  1.136960e+05  1.134500e+05   \n",
       "75%    5.007301e+06  4.989584e+06  4.813244e+06  4.758988e+06  4.698968e+06   \n",
       "max    1.311020e+09  1.303720e+09  1.296075e+09  1.288400e+09  1.280400e+09   \n",
       "\n",
       "               2001  \n",
       "count  1.085000e+03  \n",
       "mean   1.143598e+07  \n",
       "std    6.490862e+07  \n",
       "min    3.156689e+01  \n",
       "25%    5.038254e+01  \n",
       "50%    1.136410e+05  \n",
       "75%    4.535518e+06  \n",
       "max    1.271850e+09  \n",
       "\n",
       "[8 rows x 22 columns]"
      ]
     },
     "execution_count": 9,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.describe()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "cc5b58fc-fe6f-47ef-a622-ec9bd3140e0a",
   "metadata": {},
   "source": [
    "## Checking for duplicates values"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 10,
   "id": "9b6266b4-43d1-45a8-baaf-4a55ee11e02c",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "0"
      ]
     },
     "execution_count": 10,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.duplicated().sum()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "59825045-c2fc-4681-b3f8-7274943d5993",
   "metadata": {},
   "source": [
    "## Checking for missing values"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 11,
   "id": "c459c70c-fae1-4eab-871b-0977eda70aa3",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "Series Name     0\n",
       "Series Code     0\n",
       "Country Name    0\n",
       "Country Code    0\n",
       "2022            0\n",
       "2021            0\n",
       "2020            0\n",
       "2019            0\n",
       "2018            0\n",
       "2017            0\n",
       "2016            0\n",
       "2015            0\n",
       "2014            0\n",
       "2013            0\n",
       "2012            0\n",
       "2011            0\n",
       "2010            0\n",
       "2009            0\n",
       "2008            0\n",
       "2007            0\n",
       "2006            0\n",
       "2005            0\n",
       "2004            0\n",
       "2003            0\n",
       "2002            0\n",
       "2001            0\n",
       "dtype: int64"
      ]
     },
     "execution_count": 11,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.isna().sum()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "bb91e6ce-e945-4849-b572-7a665b6f1c01",
   "metadata": {},
   "source": [
    "## Checking unique values for columns"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 14,
   "id": "fbd485c0-8fd3-4295-ad7c-8aed3a7558f7",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "['Afghanistan' 'Albania' 'Algeria' 'American Samoa' 'Andorra' 'Angola'\n",
      " 'Antigua and Barbuda' 'Argentina' 'Armenia' 'Aruba' 'Australia' 'Austria'\n",
      " 'Azerbaijan' 'Bahamas, The' 'Bahrain' 'Bangladesh' 'Barbados' 'Belarus'\n",
      " 'Belgium' 'Belize' 'Benin' 'Bermuda' 'Bhutan' 'Bolivia'\n",
      " 'Bosnia and Herzegovina' 'Botswana' 'Brazil' 'British Virgin Islands'\n",
      " 'Brunei Darussalam' 'Bulgaria' 'Burkina Faso' 'Burundi' 'Cabo Verde'\n",
      " 'Cambodia' 'Cameroon' 'Canada' 'Cayman Islands'\n",
      " 'Central African Republic' 'Chad' 'Channel Islands' 'Chile' 'China'\n",
      " 'Colombia' 'Comoros' 'Congo, Dem. Rep.' 'Congo, Rep.' 'Costa Rica'\n",
      " \"Cote d'Ivoire\" 'Croatia' 'Cuba' 'Curacao' 'Cyprus' 'Czechia' 'Denmark'\n",
      " 'Djibouti' 'Dominica' 'Dominican Republic' 'Ecuador' 'Egypt, Arab Rep.'\n",
      " 'El Salvador' 'Equatorial Guinea' 'Eritrea' 'Estonia' 'Eswatini'\n",
      " 'Ethiopia' 'Faroe Islands' 'Fiji' 'Finland' 'France' 'French Polynesia'\n",
      " 'Gabon' 'Gambia, The' 'Georgia' 'Germany' 'Ghana' 'Gibraltar' 'Greece'\n",
      " 'Greenland' 'Grenada' 'Guam' 'Guatemala' 'Guinea' 'Guinea-Bissau'\n",
      " 'Guyana' 'Haiti' 'Honduras' 'Hong Kong SAR, China' 'Hungary' 'Iceland'\n",
      " 'India' 'Indonesia' 'Iran, Islamic Rep.' 'Iraq' 'Ireland' 'Isle of Man'\n",
      " 'Israel' 'Italy' 'Jamaica' 'Japan' 'Jordan' 'Kazakhstan' 'Kenya'\n",
      " 'Kiribati' \"Korea, Dem. People's Rep.\" 'Korea, Rep.' 'Kosovo' 'Kuwait'\n",
      " 'Kyrgyz Republic' 'Lao PDR' 'Latvia' 'Lebanon' 'Lesotho' 'Liberia'\n",
      " 'Libya' 'Liechtenstein' 'Lithuania' 'Luxembourg' 'Macao SAR, China'\n",
      " 'Madagascar' 'Malawi' 'Malaysia' 'Maldives' 'Mali' 'Malta'\n",
      " 'Marshall Islands' 'Mauritania' 'Mauritius' 'Mexico'\n",
      " 'Micronesia, Fed. Sts.' 'Moldova' 'Monaco' 'Mongolia' 'Montenegro'\n",
      " 'Morocco' 'Mozambique' 'Myanmar' 'Namibia' 'Nauru' 'Nepal' 'Netherlands'\n",
      " 'New Caledonia' 'New Zealand' 'Nicaragua' 'Niger' 'Nigeria'\n",
      " 'North Macedonia' 'Northern Mariana Islands' 'Norway' 'Oman' 'Pakistan'\n",
      " 'Palau' 'Panama' 'Papua New Guinea' 'Paraguay' 'Peru' 'Philippines'\n",
      " 'Poland' 'Portugal' 'Puerto Rico' 'Qatar' 'Romania' 'Russian Federation'\n",
      " 'Rwanda' 'Samoa' 'San Marino' 'Sao Tome and Principe' 'Saudi Arabia'\n",
      " 'Senegal' 'Serbia' 'Seychelles' 'Sierra Leone' 'Singapore'\n",
      " 'Sint Maarten (Dutch part)' 'Slovak Republic' 'Slovenia'\n",
      " 'Solomon Islands' 'Somalia' 'South Africa' 'South Sudan' 'Spain'\n",
      " 'Sri Lanka' 'St. Kitts and Nevis' 'St. Lucia' 'St. Martin (French part)'\n",
      " 'St. Vincent and the Grenadines' 'Sudan' 'Suriname' 'Sweden'\n",
      " 'Switzerland' 'Syrian Arab Republic' 'Tajikistan' 'Tanzania' 'Thailand'\n",
      " 'Timor-Leste' 'Togo' 'Tonga' 'Trinidad and Tobago' 'Tunisia' 'Turkiye'\n",
      " 'Turkmenistan' 'Turks and Caicos Islands' 'Tuvalu' 'Uganda' 'Ukraine'\n",
      " 'United Arab Emirates' 'United Kingdom' 'United States' 'Uruguay'\n",
      " 'Uzbekistan' 'Vanuatu' 'Venezuela, RB' 'Vietnam' 'Virgin Islands (U.S.)'\n",
      " 'West Bank and Gaza' 'Yemen, Rep.' 'Zambia' 'Zimbabwe']\n",
      "\n",
      " Total no of unique countries: 217\n"
     ]
    }
   ],
   "source": [
    "print(df['Country Name'].unique())\n",
    "print(\"\\n Total no of unique countries:\",df['Country Name'].nunique())"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 15,
   "id": "c16a26d4-0c82-4ce8-abe6-43175c41295c",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "['AFG' 'ALB' 'DZA' 'ASM' 'AND' 'AGO' 'ATG' 'ARG' 'ARM' 'ABW' 'AUS' 'AUT'\n",
      " 'AZE' 'BHS' 'BHR' 'BGD' 'BRB' 'BLR' 'BEL' 'BLZ' 'BEN' 'BMU' 'BTN' 'BOL'\n",
      " 'BIH' 'BWA' 'BRA' 'VGB' 'BRN' 'BGR' 'BFA' 'BDI' 'CPV' 'KHM' 'CMR' 'CAN'\n",
      " 'CYM' 'CAF' 'TCD' 'CHI' 'CHL' 'CHN' 'COL' 'COM' 'COD' 'COG' 'CRI' 'CIV'\n",
      " 'HRV' 'CUB' 'CUW' 'CYP' 'CZE' 'DNK' 'DJI' 'DMA' 'DOM' 'ECU' 'EGY' 'SLV'\n",
      " 'GNQ' 'ERI' 'EST' 'SWZ' 'ETH' 'FRO' 'FJI' 'FIN' 'FRA' 'PYF' 'GAB' 'GMB'\n",
      " 'GEO' 'DEU' 'GHA' 'GIB' 'GRC' 'GRL' 'GRD' 'GUM' 'GTM' 'GIN' 'GNB' 'GUY'\n",
      " 'HTI' 'HND' 'HKG' 'HUN' 'ISL' 'IND' 'IDN' 'IRN' 'IRQ' 'IRL' 'IMN' 'ISR'\n",
      " 'ITA' 'JAM' 'JPN' 'JOR' 'KAZ' 'KEN' 'KIR' 'PRK' 'KOR' 'XKX' 'KWT' 'KGZ'\n",
      " 'LAO' 'LVA' 'LBN' 'LSO' 'LBR' 'LBY' 'LIE' 'LTU' 'LUX' 'MAC' 'MDG' 'MWI'\n",
      " 'MYS' 'MDV' 'MLI' 'MLT' 'MHL' 'MRT' 'MUS' 'MEX' 'FSM' 'MDA' 'MCO' 'MNG'\n",
      " 'MNE' 'MAR' 'MOZ' 'MMR' 'NAM' 'NRU' 'NPL' 'NLD' 'NCL' 'NZL' 'NIC' 'NER'\n",
      " 'NGA' 'MKD' 'MNP' 'NOR' 'OMN' 'PAK' 'PLW' 'PAN' 'PNG' 'PRY' 'PER' 'PHL'\n",
      " 'POL' 'PRT' 'PRI' 'QAT' 'ROU' 'RUS' 'RWA' 'WSM' 'SMR' 'STP' 'SAU' 'SEN'\n",
      " 'SRB' 'SYC' 'SLE' 'SGP' 'SXM' 'SVK' 'SVN' 'SLB' 'SOM' 'ZAF' 'SSD' 'ESP'\n",
      " 'LKA' 'KNA' 'LCA' 'MAF' 'VCT' 'SDN' 'SUR' 'SWE' 'CHE' 'SYR' 'TJK' 'TZA'\n",
      " 'THA' 'TLS' 'TGO' 'TON' 'TTO' 'TUN' 'TUR' 'TKM' 'TCA' 'TUV' 'UGA' 'UKR'\n",
      " 'ARE' 'GBR' 'USA' 'URY' 'UZB' 'VUT' 'VEN' 'VNM' 'VIR' 'PSE' 'YEM' 'ZMB'\n",
      " 'ZWE']\n",
      "\n",
      " Total no of unique country code: 217\n"
     ]
    }
   ],
   "source": [
    "print(df['Country Code'].unique())\n",
    "print(\"\\n Total no of unique country code:\",df['Country Code'].nunique())"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "24e5cddb-607e-4ed3-b559-ee93d0cb85d3",
   "metadata": {},
   "source": [
    "## Dropping unnecessary columns"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 16,
   "id": "ecd6b30c-a079-4baf-9cae-f67c64ce350e",
   "metadata": {},
   "outputs": [],
   "source": [
    "df.drop(['Series Name','Country Name'],axis=1,inplace=True)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "60b74ed3-f38a-4a79-b5b4-d852cbbd5596",
   "metadata": {},
   "source": [
    "## Extarction of top 10 countries with respect to total population"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 27,
   "id": "cec5f782-f1c2-40c5-8c3b-53428669827b",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Top ten countries of total population\n",
      "\n",
      "    Country Code\n",
      "89           IND\n",
      "41           CHN\n",
      "206          USA\n",
      "90           IDN\n",
      "149          PAK\n",
      "144          NGA\n",
      "26           BRA\n",
      "15           BGD\n",
      "161          RUS\n",
      "127          MEX\n"
     ]
    }
   ],
   "source": [
    "# Filter data for total population\n",
    "total_population_data = df[df['Series Code'] == 'SP.POP.TOTL']\n",
    "\n",
    "# Sort data based on the total population for 2022\n",
    "total_population_sorted = total_population_data.sort_values(by=\"2022\", ascending=False)\n",
    "\n",
    "# Get the top ten countries with the highest total population for 2022\n",
    "total_top_ten_countries = total_population_sorted.head(10)\n",
    "print(\"Top ten countries of total population\\n\")\n",
    "print(total_top_ten_countries[['Country Code']])"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "4629dc34-b032-4851-9ba1-ed944a3524f4",
   "metadata": {},
   "source": [
    "# Bar Plot\n"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "3b73cea9-a3dd-4815-ad40-3aeb26b367c8",
   "metadata": {},
   "source": [
    "## Top ten countries of total population in year 2022 and 2016"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 30,
   "id": "86fbd4db-fba4-4814-a606-cf8f614558aa",
   "metadata": {},
   "outputs": [
    {
     "name": "stderr",
     "output_type": "stream",
     "text": [
      "C:\\Users\\hp\\AppData\\Local\\Temp\\ipykernel_4572\\1671410998.py:4: FutureWarning: \n",
      "\n",
      "Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `y` variable to `hue` and set `legend=False` for the same effect.\n",
      "\n",
      "  sns.barplot(x=\"2022\", y=\"Country Code\", data=total_top_ten_countries, palette=\"coolwarm\")\n"
     ]
    },
    {
     "data": {
      "image/png": 
      "text/plain": [
       "<Figure size 1500x600 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    },
    {
     "name": "stderr",
     "output_type": "stream",
     "text": [
      "C:\\Users\\hp\\AppData\\Local\\Temp\\ipykernel_4572\\1671410998.py:13: FutureWarning: \n",
      "\n",
      "Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `y` variable to `hue` and set `legend=False` for the same effect.\n",
      "\n",
      "  sns.barplot(x=\"2016\", y=\"Country Code\", data=total_top_ten_countries, palette=\"coolwarm\")\n"
     ]
    },
    {
     "data": {
      "image/png": 
       "<Figure size 1500x600 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "# Create the bar plot\n",
    "plt.figure(figsize=(15, 6))\n",
    "plt.subplot(2,2,1)\n",
    "sns.barplot(x=\"2022\", y=\"Country Code\", data=total_top_ten_countries, palette=\"coolwarm\")\n",
    "plt.title(\"Top Ten Countries of Total Population (2022)\",fontsize=10)\n",
    "plt.xlabel(\"Total Population\",fontsize=10)\n",
    "plt.ylabel(\"Country\",fontsize=10)\n",
    "plt.show()\n",
    "\n",
    "# Create the bar plot\n",
    "plt.figure(figsize=(15, 6))\n",
    "plt.subplot(2,2,2)\n",
    "sns.barplot(x=\"2016\", y=\"Country Code\", data=total_top_ten_countries, palette=\"coolwarm\")\n",
    "plt.title(\"Top Ten Countries of Total Population (2016)\",fontsize=10)\n",
    "plt.xlabel(\"Total Population\",fontsize=10)\n",
    "plt.ylabel(\"Country\",fontsize=10)\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "0c255985-9f1d-4c22-bc7b-b90a53e951c0",
   "metadata": {},
   "source": [
    "## Extraction of bottom 10 countries with respect to total popultaion"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 36,
   "id": "86714e46-073b-4a48-ac89-84362fe3133d",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Bottom ten countries of total population\n",
      "\n",
      "    Country Code\n",
      "201          TUV\n",
      "137          NRU\n",
      "150          PLW\n",
      "27           VGB\n",
      "183          MAF\n",
      "75           GIB\n",
      "164          SMR\n",
      "130          MCO\n",
      "114          LIE\n",
      "124          MHL\n"
     ]
    }
   ],
   "source": [
    "# Sort data based on the total population for 2022\n",
    "total_population_sorted1 = total_population_data.sort_values(by=\"2022\", ascending=True)\n",
    "\n",
    "# Get the top ten countries with the highest total population for 2022\n",
    "total_bottom_ten_countries = total_population_sorted1.head(10)\n",
    "print(\"Bottom ten countries of total population\\n\")\n",
    "print(total_bottom_ten_countries[['Country Code']])"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "18eeb3c2-7fe0-43df-a16f-70df775510c1",
   "metadata": {},
   "source": [
    "## Bottom ten countries of total population in year 2022 and 2016"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 37,
   "id": "5f9b2fdc-db0b-403b-801d-a37308f7e5b8",
   "metadata": {},
   "outputs": [
    {
     "name": "stderr",
     "output_type": "stream",
     "text": [
      "C:\\Users\\hp\\AppData\\Local\\Temp\\ipykernel_4572\\1344369931.py:4: FutureWarning: \n",
      "\n",
      "Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `y` variable to `hue` and set `legend=False` for the same effect.\n",
      "\n",
      "  sns.barplot(x=\"2022\", y=\"Country Code\", data=total_bottom_ten_countries, palette=\"coolwarm\")\n"
     ]
    },
    {
     "data": {
      "image/png": 
      "text/plain": [
       "<Figure size 1500x600 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    },
    {
     "name": "stderr",
     "output_type": "stream",
     "text": [
      "C:\\Users\\hp\\AppData\\Local\\Temp\\ipykernel_4572\\1344369931.py:13: FutureWarning: \n",
      "\n",
      "Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `y` variable to `hue` and set `legend=False` for the same effect.\n",
      "\n",
      "  sns.barplot(x=\"2016\", y=\"Country Code\", data=total_bottom_ten_countries, palette=\"coolwarm\")\n"
     ]
    },
    {
     "data": {
      "image/png": 
      "text/plain": [
       "<Figure size 1500x600 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "# Create the bar plot\n",
    "plt.figure(figsize=(15, 6))\n",
    "plt.subplot(2,2,1)\n",
    "sns.barplot(x=\"2022\", y=\"Country Code\", data=total_bottom_ten_countries, palette=\"coolwarm\")\n",
    "plt.title(\"Bottom Ten Countries of Total Population (2022)\",fontsize=10)\n",
    "plt.xlabel(\"Total Population\",fontsize=10)\n",
    "plt.ylabel(\"Country\",fontsize=10)\n",
    "plt.show()\n",
    "\n",
    "# Create the bar plot\n",
    "plt.figure(figsize=(15, 6))\n",
    "plt.subplot(2,2,2)\n",
    "sns.barplot(x=\"2016\", y=\"Country Code\", data=total_bottom_ten_countries, palette=\"coolwarm\")\n",
    "plt.title(\"Bottom Ten Countries of Total Population (2016)\",fontsize=10)\n",
    "plt.xlabel(\"Total Population\",fontsize=10)\n",
    "plt.ylabel(\"Country\",fontsize=10)\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "e4916ab0-8f1e-4b13-9ef5-006f541c2cd5",
   "metadata": {},
   "source": [
    "## Extarction of top 10 countries with highest male population"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 38,
   "id": "2900a3ec-e182-4e24-aaff-4d24345bcf21",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Top ten countries of male population\n",
      "    Country Code\n",
      "523          IND\n",
      "475          CHN\n",
      "640          USA\n",
      "524          IDN\n",
      "583          PAK\n",
      "578          NGA\n",
      "460          BRA\n",
      "449          BGD\n",
      "595          RUS\n",
      "561          MEX\n"
     ]
    }
   ],
   "source": [
    "#filter data for male population\n",
    "male_population_data = df[df['Series Code']=='SP.POP.TOTL.MA.IN']\n",
    "\n",
    "#sort data based on the male population for 2022\n",
    "male_population_sorted =male_population_data.sort_values(by=\"2022\",ascending=False)\n",
    "\n",
    "#Get the top 10 countries with the highest male population for 2022\n",
    "male_top_ten_countries = male_population_sorted .head(10)\n",
    "print(\"Top ten countries of male population\")\n",
    "print(male_top_ten_countries[['Country Code']])"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 39,
   "id": "5d183eab-f1bd-4017-95b4-690e17604d35",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Top ten countries of female population\n",
      "    Country Code\n",
      "258          CHN\n",
      "306          IND\n",
      "423          USA\n",
      "307          IDN\n",
      "366          PAK\n",
      "243          BRA\n",
      "361          NGA\n",
      "232          BGD\n",
      "378          RUS\n",
      "344          MEX\n"
     ]
    }
   ],
   "source": [
    "#filter data for male population\n",
    "female_population_data = df[df['Series Code']=='SP.POP.TOTL.FE.IN']\n",
    "\n",
    "#sort data based on the male population for 2022\n",
    "female_population_sorted =female_population_data.sort_values(by=\"2022\",ascending=False)\n",
    "\n",
    "#Get the top 10 countries with the highest male population for 2022\n",
    "female_top_ten_countries = female_population_sorted .head(10)\n",
    "print(\"Top ten countries of female population\")\n",
    "print(female_top_ten_countries[['Country Code']])"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "bd25460e-48b5-4e80-9b6a-cf8b6d7bc8dd",
   "metadata": {},
   "source": [
    "## Top ten countries with highest male and female population in 2022"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 40,
   "id": "aad94883-ca24-4934-990a-57d2e014053b",
   "metadata": {},
   "outputs": [
    {
     "name": "stderr",
     "output_type": "stream",
     "text": [
      "C:\\Users\\hp\\AppData\\Local\\Temp\\ipykernel_4572\\34499514.py:4: FutureWarning: \n",
      "\n",
      "Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `y` variable to `hue` and set `legend=False` for the same effect.\n",
      "\n",
      "  sns.barplot(x=\"2022\", y=\"Country Code\", data=male_top_ten_countries, palette=\"viridis\")\n"
     ]
    },
    {
     "data": {
      "image/png": 
      "text/plain": [
       "<Figure size 1500x600 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    },
    {
     "name": "stderr",
     "output_type": "stream",
     "text": [
      "C:\\Users\\hp\\AppData\\Local\\Temp\\ipykernel_4572\\34499514.py:13: FutureWarning: \n",
      "\n",
      "Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `y` variable to `hue` and set `legend=False` for the same effect.\n",
      "\n",
      "  sns.barplot(x=\"2016\", y=\"Country Code\", data=female_top_ten_countries, palette=\"viridis\")\n"
     ]
    },
    {
     "data": {
      "image/png": 
      "text/plain": [
       "<Figure size 1500x600 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "# Create the bar plot\n",
    "plt.figure(figsize=(15, 6))\n",
    "plt.subplot(2,2,1)\n",
    "sns.barplot(x=\"2022\", y=\"Country Code\", data=male_top_ten_countries, palette=\"viridis\")\n",
    "plt.title(\"Top ten conuntries of male population(2022)\",fontsize=10)\n",
    "plt.xlabel(\"Male Population\",fontsize=10)\n",
    "plt.ylabel(\"Country\",fontsize=10)\n",
    "plt.show()\n",
    "\n",
    "# Create the bar plot\n",
    "plt.figure(figsize=(15, 6))\n",
    "plt.subplot(2,2,2)\n",
    "sns.barplot(x=\"2016\", y=\"Country Code\", data=female_top_ten_countries, palette=\"viridis\")\n",
    "plt.title(\"Top ten conuntries of female population(2022)\",fontsize=10)\n",
    "plt.xlabel(\"Female Population\",fontsize=10)\n",
    "plt.ylabel(\"Country\",fontsize=10)\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "4417dc1a-c9da-4254-be93-b83ee16e71f2",
   "metadata": {},
   "source": [
    "# Stacked Bar Plot"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "2dee60a7-a485-4bff-96b5-295a93371f47",
   "metadata": {},
   "source": [
    "## Top 10 countries with male and female population"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 44,
   "id": "91a5f88a-f318-4205-927a-51341ed609f2",
   "metadata": {},
   "outputs": [],
   "source": [
    "#merge male and female population data on 'Country Code'\n",
    "merge_data=pd.merge(male_population_data,female_population_data,on=\"Country Code\",suffixes=(\"_male\",\"_female\"))"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 48,
   "id": "b55ce3ec-f2bf-4960-8730-3d0b7834d399",
   "metadata": {},
   "outputs": [],
   "source": [
    "#merged data\n",
    "#calculate the total population for each country (male + female)\n",
    "merge_data[\"Total population\"] = merge_data[\"2022_male\"] + merge_data [\"2022_female\"]"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 49,
   "id": "46beddaa-b421-48fc-8dfc-417dd709aab2",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>Series Code_male</th>\n",
       "      <th>Country Code</th>\n",
       "      <th>2022_male</th>\n",
       "      <th>2021_male</th>\n",
       "      <th>2020_male</th>\n",
       "      <th>2019_male</th>\n",
       "      <th>2018_male</th>\n",
       "      <th>2017_male</th>\n",
       "      <th>2016_male</th>\n",
       "      <th>2015_male</th>\n",
       "      <th>...</th>\n",
       "      <th>2009_female</th>\n",
       "      <th>2008_female</th>\n",
       "      <th>2007_female</th>\n",
       "      <th>2006_female</th>\n",
       "      <th>2005_female</th>\n",
       "      <th>2004_female</th>\n",
       "      <th>2003_female</th>\n",
       "      <th>2002_female</th>\n",
       "      <th>2001_female</th>\n",
       "      <th>Total population</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>SP.POP.TOTL.MA.IN</td>\n",
       "      <td>AFG</td>\n",
       "      <td>20766442.0</td>\n",
       "      <td>20254878.0</td>\n",
       "      <td>19692301.0</td>\n",
       "      <td>19090409.0</td>\n",
       "      <td>18549862.0</td>\n",
       "      <td>18028696.0</td>\n",
       "      <td>17520861.0</td>\n",
       "      <td>17071446.0</td>\n",
       "      <td>...</td>\n",
       "      <td>13557331.0</td>\n",
       "      <td>13088192.0</td>\n",
       "      <td>12835340.0</td>\n",
       "      <td>12614497.0</td>\n",
       "      <td>12109086.0</td>\n",
       "      <td>11690825.0</td>\n",
       "      <td>11247647.0</td>\n",
       "      <td>10438055.0</td>\n",
       "      <td>9793166.0</td>\n",
       "      <td>41128771.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>SP.POP.TOTL.MA.IN</td>\n",
       "      <td>ALB</td>\n",
       "      <td>1384548.0</td>\n",
       "      <td>1404454.0</td>\n",
       "      <td>1419264.0</td>\n",
       "      <td>1428828.0</td>\n",
       "      <td>1435881.0</td>\n",
       "      <td>1440219.0</td>\n",
       "      <td>1442176.0</td>\n",
       "      <td>1444890.0</td>\n",
       "      <td>...</td>\n",
       "      <td>1462978.0</td>\n",
       "      <td>1474838.0</td>\n",
       "      <td>1488396.0</td>\n",
       "      <td>1501918.0</td>\n",
       "      <td>1513578.0</td>\n",
       "      <td>1523393.0</td>\n",
       "      <td>1531532.0</td>\n",
       "      <td>1538490.0</td>\n",
       "      <td>1543533.0</td>\n",
       "      <td>2775633.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>SP.POP.TOTL.MA.IN</td>\n",
       "      <td>DZA</td>\n",
       "      <td>22862237.0</td>\n",
       "      <td>22497244.0</td>\n",
       "      <td>22132899.0</td>\n",
       "      <td>21756903.0</td>\n",
       "      <td>21362603.0</td>\n",
       "      <td>20961313.0</td>\n",
       "      <td>20556314.0</td>\n",
       "      <td>20152232.0</td>\n",
       "      <td>...</td>\n",
       "      <td>17249096.0</td>\n",
       "      <td>16941031.0</td>\n",
       "      <td>16653361.0</td>\n",
       "      <td>16384158.0</td>\n",
       "      <td>16150274.0</td>\n",
       "      <td>15932047.0</td>\n",
       "      <td>15709725.0</td>\n",
       "      <td>15497822.0</td>\n",
       "      <td>15288132.0</td>\n",
       "      <td>44903224.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>SP.POP.TOTL.MA.IN</td>\n",
       "      <td>ASM</td>\n",
       "      <td>21873.0</td>\n",
       "      <td>22289.0</td>\n",
       "      <td>22921.0</td>\n",
       "      <td>23535.0</td>\n",
       "      <td>24134.0</td>\n",
       "      <td>24701.0</td>\n",
       "      <td>25240.0</td>\n",
       "      <td>25739.0</td>\n",
       "      <td>...</td>\n",
       "      <td>27406.0</td>\n",
       "      <td>27626.0</td>\n",
       "      <td>27842.0</td>\n",
       "      <td>28044.0</td>\n",
       "      <td>28230.0</td>\n",
       "      <td>28392.0</td>\n",
       "      <td>28521.0</td>\n",
       "      <td>28608.0</td>\n",
       "      <td>28649.0</td>\n",
       "      <td>44272.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>SP.POP.TOTL.MA.IN</td>\n",
       "      <td>AND</td>\n",
       "      <td>40786.0</td>\n",
       "      <td>40361.0</td>\n",
       "      <td>39615.0</td>\n",
       "      <td>38842.0</td>\n",
       "      <td>38071.0</td>\n",
       "      <td>37380.0</td>\n",
       "      <td>36628.0</td>\n",
       "      <td>36188.0</td>\n",
       "      <td>...</td>\n",
       "      <td>36065.0</td>\n",
       "      <td>36864.0</td>\n",
       "      <td>37633.0</td>\n",
       "      <td>38392.0</td>\n",
       "      <td>38147.0</td>\n",
       "      <td>36852.0</td>\n",
       "      <td>35478.0</td>\n",
       "      <td>34076.0</td>\n",
       "      <td>32669.0</td>\n",
       "      <td>79824.0</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "<p>5 rows × 48 columns</p>\n",
       "</div>"
      ],
      "text/plain": [
       "    Series Code_male Country Code   2022_male   2021_male   2020_male  \\\n",
       "0  SP.POP.TOTL.MA.IN          AFG  20766442.0  20254878.0  19692301.0   \n",
       "1  SP.POP.TOTL.MA.IN          ALB   1384548.0   1404454.0   1419264.0   \n",
       "2  SP.POP.TOTL.MA.IN          DZA  22862237.0  22497244.0  22132899.0   \n",
       "3  SP.POP.TOTL.MA.IN          ASM     21873.0     22289.0     22921.0   \n",
       "4  SP.POP.TOTL.MA.IN          AND     40786.0     40361.0     39615.0   \n",
       "\n",
       "    2019_male   2018_male   2017_male   2016_male   2015_male  ...  \\\n",
       "0  19090409.0  18549862.0  18028696.0  17520861.0  17071446.0  ...   \n",
       "1   1428828.0   1435881.0   1440219.0   1442176.0   1444890.0  ...   \n",
       "2  21756903.0  21362603.0  20961313.0  20556314.0  20152232.0  ...   \n",
       "3     23535.0     24134.0     24701.0     25240.0     25739.0  ...   \n",
       "4     38842.0     38071.0     37380.0     36628.0     36188.0  ...   \n",
       "\n",
       "   2009_female  2008_female  2007_female  2006_female  2005_female  \\\n",
       "0   13557331.0   13088192.0   12835340.0   12614497.0   12109086.0   \n",
       "1    1462978.0    1474838.0    1488396.0    1501918.0    1513578.0   \n",
       "2   17249096.0   16941031.0   16653361.0   16384158.0   16150274.0   \n",
       "3      27406.0      27626.0      27842.0      28044.0      28230.0   \n",
       "4      36065.0      36864.0      37633.0      38392.0      38147.0   \n",
       "\n",
       "   2004_female  2003_female  2002_female  2001_female  Total population  \n",
       "0   11690825.0   11247647.0   10438055.0    9793166.0        41128771.0  \n",
       "1    1523393.0    1531532.0    1538490.0    1543533.0         2775633.0  \n",
       "2   15932047.0   15709725.0   15497822.0   15288132.0        44903224.0  \n",
       "3      28392.0      28521.0      28608.0      28649.0           44272.0  \n",
       "4      36852.0      35478.0      34076.0      32669.0           79824.0  \n",
       "\n",
       "[5 rows x 48 columns]"
      ]
     },
     "execution_count": 49,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "merge_data.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 51,
   "id": "493efee3-dcbb-4181-a60f-1bacb87c1e3c",
   "metadata": {},
   "outputs": [],
   "source": [
    "#sort data based on total population in descending order\n",
    "sorted_data = merge_data.sort_values(by=\"Total population\", ascending=False)\n"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "d74dc131-bf69-48d4-bcc9-0cc32e2ae059",
   "metadata": {},
   "source": [
    "## Select the top 10 countries with the highest total population"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 52,
   "id": "61c74bd8-caf9-4e02-a33c-6d324e86742f",
   "metadata": {},
   "outputs": [],
   "source": [
    "top_10_countries = sorted_data.head(10)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 54,
   "id": "881c2ba8-0763-4565-a1b6-50ea2c0d2651",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": 
      "text/plain": [
       "<Figure size 1200x600 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "#create the staked bar plot\n",
    "plt.figure(figsize=(12,6))\n",
    "sns.barplot(x=\"Country Code\",y=\"2022_female\",data=top_10_countries,color=\"red\",label=\"female Population\")\n",
    "sns.barplot(x=\"Country Code\",y=\"2022_male\",data=top_10_countries,bottom=top_10_countries[\"2022_female\"],color=\"green\",label=\"Male Population\")\n",
    "plt.xlabel(\"Country\")\n",
    "plt.ylabel(\"Population\")\n",
    "plt.legend()\n",
    "plt.xticks(rotation=45,ha=\"right\")\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "5ae2a1b5-0d59-4a4b-b6db-fec125b15235",
   "metadata": {},
   "source": [
    "## Bottom 10 countries with male and female population(2022)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 56,
   "id": "697dce0e-e515-43d9-a541-256c86008e8b",
   "metadata": {},
   "outputs": [],
   "source": [
    "#select the top 10 countries with the highest total population\n",
    "bottom_10_countries = sorted_data.tail(10)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 59,
   "id": "0090910e-dc47-4636-9d2a-63ee45b9d480",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": 
      "text/plain": [
       "<Figure size 1200x600 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "# Create the stacked bar plot\n",
    "plt.figure(figsize=(12, 6))\n",
    "sns.barplot(x=\"Country Code\", y=\"2022_female\", data=bottom_10_countries, color=\"red\", label=\"Female Population\")\n",
    "sns.barplot(x=\"Country Code\", y=\"2022_male\", data=bottom_10_countries, bottom=bottom_10_countries[\"2022_female\"], color=\"green\", label=\"Male Population\")\n",
    "plt.xlabel(\"Country\")\n",
    "plt.ylabel(\"Population\")\n",
    "plt.legend()\n",
    "plt.xticks(rotation=45, ha=\"right\")\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "4a3f44d8-d756-4db6-b474-e640caf45788",
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3 (ipykernel)",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.10.11"
  },
  "widgets": {
   "application/vnd.jupyter.widget-state+json": {
    "state": {},
    "version_major": 2,
    "version_minor": 0
   }
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}
