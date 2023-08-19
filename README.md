# Diwali-Sales-Analysis
Import the data using pandas library and visualize data according to the states and areas,age.
{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 1,
   "id": "389f397d",
   "metadata": {},
   "outputs": [],
   "source": [
    "# Import python libraries\n",
    "import numpy as np\n",
    "import pandas as pd\n",
    "import matplotlib.pyplot as plt\n",
    "%matplotlib inline\n",
    "import seaborn as sns"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 6,
   "id": "18638e77",
   "metadata": {},
   "outputs": [],
   "source": [
    "# import csv file\n",
    "df=pd.read_csv('D:\\Python\\Projects\\Diwali Sales Data.csv',encoding='unicode_escape')"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 8,
   "id": "83f0f57b",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "(11251, 15)"
      ]
     },
     "execution_count": 8,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.shape"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 9,
   "id": "a6e960e4",
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
       "      <th>User_ID</th>\n",
       "      <th>Cust_name</th>\n",
       "      <th>Product_ID</th>\n",
       "      <th>Gender</th>\n",
       "      <th>Age Group</th>\n",
       "      <th>Age</th>\n",
       "      <th>Marital_Status</th>\n",
       "      <th>State</th>\n",
       "      <th>Zone</th>\n",
       "      <th>Occupation</th>\n",
       "      <th>Product_Category</th>\n",
       "      <th>Orders</th>\n",
       "      <th>Amount</th>\n",
       "      <th>Status</th>\n",
       "      <th>unnamed1</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>1002903</td>\n",
       "      <td>Sanskriti</td>\n",
       "      <td>P00125942</td>\n",
       "      <td>F</td>\n",
       "      <td>26-35</td>\n",
       "      <td>28</td>\n",
       "      <td>0</td>\n",
       "      <td>Maharashtra</td>\n",
       "      <td>Western</td>\n",
       "      <td>Healthcare</td>\n",
       "      <td>Auto</td>\n",
       "      <td>1</td>\n",
       "      <td>23952.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>1000732</td>\n",
       "      <td>Kartik</td>\n",
       "      <td>P00110942</td>\n",
       "      <td>F</td>\n",
       "      <td>26-35</td>\n",
       "      <td>35</td>\n",
       "      <td>1</td>\n",
       "      <td>Andhra Pradesh</td>\n",
       "      <td>Southern</td>\n",
       "      <td>Govt</td>\n",
       "      <td>Auto</td>\n",
       "      <td>3</td>\n",
       "      <td>23934.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>1001990</td>\n",
       "      <td>Bindu</td>\n",
       "      <td>P00118542</td>\n",
       "      <td>F</td>\n",
       "      <td>26-35</td>\n",
       "      <td>35</td>\n",
       "      <td>1</td>\n",
       "      <td>Uttar Pradesh</td>\n",
       "      <td>Central</td>\n",
       "      <td>Automobile</td>\n",
       "      <td>Auto</td>\n",
       "      <td>3</td>\n",
       "      <td>23924.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>1001425</td>\n",
       "      <td>Sudevi</td>\n",
       "      <td>P00237842</td>\n",
       "      <td>M</td>\n",
       "      <td>0-17</td>\n",
       "      <td>16</td>\n",
       "      <td>0</td>\n",
       "      <td>Karnataka</td>\n",
       "      <td>Southern</td>\n",
       "      <td>Construction</td>\n",
       "      <td>Auto</td>\n",
       "      <td>2</td>\n",
       "      <td>23912.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>1000588</td>\n",
       "      <td>Joni</td>\n",
       "      <td>P00057942</td>\n",
       "      <td>M</td>\n",
       "      <td>26-35</td>\n",
       "      <td>28</td>\n",
       "      <td>1</td>\n",
       "      <td>Gujarat</td>\n",
       "      <td>Western</td>\n",
       "      <td>Food Processing</td>\n",
       "      <td>Auto</td>\n",
       "      <td>2</td>\n",
       "      <td>23877.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "   User_ID  Cust_name Product_ID Gender Age Group  Age  Marital_Status  \\\n",
       "0  1002903  Sanskriti  P00125942      F     26-35   28               0   \n",
       "1  1000732     Kartik  P00110942      F     26-35   35               1   \n",
       "2  1001990      Bindu  P00118542      F     26-35   35               1   \n",
       "3  1001425     Sudevi  P00237842      M      0-17   16               0   \n",
       "4  1000588       Joni  P00057942      M     26-35   28               1   \n",
       "\n",
       "            State      Zone       Occupation Product_Category  Orders  \\\n",
       "0     Maharashtra   Western       Healthcare             Auto       1   \n",
       "1  Andhra Pradesh  Southern             Govt             Auto       3   \n",
       "2   Uttar Pradesh   Central       Automobile             Auto       3   \n",
       "3       Karnataka  Southern     Construction             Auto       2   \n",
       "4         Gujarat   Western  Food Processing             Auto       2   \n",
       "\n",
       "    Amount  Status  unnamed1  \n",
       "0  23952.0     NaN       NaN  \n",
       "1  23934.0     NaN       NaN  \n",
       "2  23924.0     NaN       NaN  \n",
       "3  23912.0     NaN       NaN  \n",
       "4  23877.0     NaN       NaN  "
      ]
     },
     "execution_count": 9,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 10,
   "id": "80c52675",
   "metadata": {},
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "<class 'pandas.core.frame.DataFrame'>\n",
      "RangeIndex: 11251 entries, 0 to 11250\n",
      "Data columns (total 15 columns):\n",
      " #   Column            Non-Null Count  Dtype  \n",
      "---  ------            --------------  -----  \n",
      " 0   User_ID           11251 non-null  int64  \n",
      " 1   Cust_name         11251 non-null  object \n",
      " 2   Product_ID        11251 non-null  object \n",
      " 3   Gender            11251 non-null  object \n",
      " 4   Age Group         11251 non-null  object \n",
      " 5   Age               11251 non-null  int64  \n",
      " 6   Marital_Status    11251 non-null  int64  \n",
      " 7   State             11251 non-null  object \n",
      " 8   Zone              11251 non-null  object \n",
      " 9   Occupation        11251 non-null  object \n",
      " 10  Product_Category  11251 non-null  object \n",
      " 11  Orders            11251 non-null  int64  \n",
      " 12  Amount            11239 non-null  float64\n",
      " 13  Status            0 non-null      float64\n",
      " 14  unnamed1          0 non-null      float64\n",
      "dtypes: float64(3), int64(4), object(8)\n",
      "memory usage: 1.3+ MB\n"
     ]
    }
   ],
   "source": [
    "df.info()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 11,
   "id": "6bb44ecb",
   "metadata": {},
   "outputs": [],
   "source": [
    "# drop blank columns\n",
    "df.drop([\"Status\",\"unnamed1\"],axis=1,inplace=True)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 12,
   "id": "47a116e1",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "User_ID              0\n",
       "Cust_name            0\n",
       "Product_ID           0\n",
       "Gender               0\n",
       "Age Group            0\n",
       "Age                  0\n",
       "Marital_Status       0\n",
       "State                0\n",
       "Zone                 0\n",
       "Occupation           0\n",
       "Product_Category     0\n",
       "Orders               0\n",
       "Amount              12\n",
       "dtype: int64"
      ]
     },
     "execution_count": 12,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# Check for null values\n",
    "pd.isnull(df).sum()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 14,
   "id": "27de860a",
   "metadata": {},
   "outputs": [],
   "source": [
    "#drop null values\n",
    "df.dropna(inplace=True)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 15,
   "id": "fa97de9b",
   "metadata": {},
   "outputs": [],
   "source": [
    "#Change data types\n",
    "df[\"Amount\"]=df[\"Amount\"].astype(\"int\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 16,
   "id": "6f41b132",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "dtype('int32')"
      ]
     },
     "execution_count": 16,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df[\"Amount\"].dtypes"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 17,
   "id": "b2cb7b9d",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "Index(['User_ID', 'Cust_name', 'Product_ID', 'Gender', 'Age Group', 'Age',\n",
       "       'Marital_Status', 'State', 'Zone', 'Occupation', 'Product_Category',\n",
       "       'Orders', 'Amount'],\n",
       "      dtype='object')"
      ]
     },
     "execution_count": 17,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.columns"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 18,
   "id": "0c8dd1f5",
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
       "      <th>User_ID</th>\n",
       "      <th>Cust_name</th>\n",
       "      <th>Product_ID</th>\n",
       "      <th>Gender</th>\n",
       "      <th>Age Group</th>\n",
       "      <th>Age</th>\n",
       "      <th>Shaadi</th>\n",
       "      <th>State</th>\n",
       "      <th>Zone</th>\n",
       "      <th>Occupation</th>\n",
       "      <th>Product_Category</th>\n",
       "      <th>Orders</th>\n",
       "      <th>Amount</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>1002903</td>\n",
       "      <td>Sanskriti</td>\n",
       "      <td>P00125942</td>\n",
       "      <td>F</td>\n",
       "      <td>26-35</td>\n",
       "      <td>28</td>\n",
       "      <td>0</td>\n",
       "      <td>Maharashtra</td>\n",
       "      <td>Western</td>\n",
       "      <td>Healthcare</td>\n",
       "      <td>Auto</td>\n",
       "      <td>1</td>\n",
       "      <td>23952</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>1000732</td>\n",
       "      <td>Kartik</td>\n",
       "      <td>P00110942</td>\n",
       "      <td>F</td>\n",
       "      <td>26-35</td>\n",
       "      <td>35</td>\n",
       "      <td>1</td>\n",
       "      <td>Andhra Pradesh</td>\n",
       "      <td>Southern</td>\n",
       "      <td>Govt</td>\n",
       "      <td>Auto</td>\n",
       "      <td>3</td>\n",
       "      <td>23934</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>1001990</td>\n",
       "      <td>Bindu</td>\n",
       "      <td>P00118542</td>\n",
       "      <td>F</td>\n",
       "      <td>26-35</td>\n",
       "      <td>35</td>\n",
       "      <td>1</td>\n",
       "      <td>Uttar Pradesh</td>\n",
       "      <td>Central</td>\n",
       "      <td>Automobile</td>\n",
       "      <td>Auto</td>\n",
       "      <td>3</td>\n",
       "      <td>23924</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>1001425</td>\n",
       "      <td>Sudevi</td>\n",
       "      <td>P00237842</td>\n",
       "      <td>M</td>\n",
       "      <td>0-17</td>\n",
       "      <td>16</td>\n",
       "      <td>0</td>\n",
       "      <td>Karnataka</td>\n",
       "      <td>Southern</td>\n",
       "      <td>Construction</td>\n",
       "      <td>Auto</td>\n",
       "      <td>2</td>\n",
       "      <td>23912</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>1000588</td>\n",
       "      <td>Joni</td>\n",
       "      <td>P00057942</td>\n",
       "      <td>M</td>\n",
       "      <td>26-35</td>\n",
       "      <td>28</td>\n",
       "      <td>1</td>\n",
       "      <td>Gujarat</td>\n",
       "      <td>Western</td>\n",
       "      <td>Food Processing</td>\n",
       "      <td>Auto</td>\n",
       "      <td>2</td>\n",
       "      <td>23877</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>...</th>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "      <td>...</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>11246</th>\n",
       "      <td>1000695</td>\n",
       "      <td>Manning</td>\n",
       "      <td>P00296942</td>\n",
       "      <td>M</td>\n",
       "      <td>18-25</td>\n",
       "      <td>19</td>\n",
       "      <td>1</td>\n",
       "      <td>Maharashtra</td>\n",
       "      <td>Western</td>\n",
       "      <td>Chemical</td>\n",
       "      <td>Office</td>\n",
       "      <td>4</td>\n",
       "      <td>370</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>11247</th>\n",
       "      <td>1004089</td>\n",
       "      <td>Reichenbach</td>\n",
       "      <td>P00171342</td>\n",
       "      <td>M</td>\n",
       "      <td>26-35</td>\n",
       "      <td>33</td>\n",
       "      <td>0</td>\n",
       "      <td>Haryana</td>\n",
       "      <td>Northern</td>\n",
       "      <td>Healthcare</td>\n",
       "      <td>Veterinary</td>\n",
       "      <td>3</td>\n",
       "      <td>367</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>11248</th>\n",
       "      <td>1001209</td>\n",
       "      <td>Oshin</td>\n",
       "      <td>P00201342</td>\n",
       "      <td>F</td>\n",
       "      <td>36-45</td>\n",
       "      <td>40</td>\n",
       "      <td>0</td>\n",
       "      <td>Madhya Pradesh</td>\n",
       "      <td>Central</td>\n",
       "      <td>Textile</td>\n",
       "      <td>Office</td>\n",
       "      <td>4</td>\n",
       "      <td>213</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>11249</th>\n",
       "      <td>1004023</td>\n",
       "      <td>Noonan</td>\n",
       "      <td>P00059442</td>\n",
       "      <td>M</td>\n",
       "      <td>36-45</td>\n",
       "      <td>37</td>\n",
       "      <td>0</td>\n",
       "      <td>Karnataka</td>\n",
       "      <td>Southern</td>\n",
       "      <td>Agriculture</td>\n",
       "      <td>Office</td>\n",
       "      <td>3</td>\n",
       "      <td>206</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>11250</th>\n",
       "      <td>1002744</td>\n",
       "      <td>Brumley</td>\n",
       "      <td>P00281742</td>\n",
       "      <td>F</td>\n",
       "      <td>18-25</td>\n",
       "      <td>19</td>\n",
       "      <td>0</td>\n",
       "      <td>Maharashtra</td>\n",
       "      <td>Western</td>\n",
       "      <td>Healthcare</td>\n",
       "      <td>Office</td>\n",
       "      <td>3</td>\n",
       "      <td>188</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "<p>11239 rows × 13 columns</p>\n",
       "</div>"
      ],
      "text/plain": [
       "       User_ID    Cust_name Product_ID Gender Age Group  Age  Shaadi  \\\n",
       "0      1002903    Sanskriti  P00125942      F     26-35   28       0   \n",
       "1      1000732       Kartik  P00110942      F     26-35   35       1   \n",
       "2      1001990        Bindu  P00118542      F     26-35   35       1   \n",
       "3      1001425       Sudevi  P00237842      M      0-17   16       0   \n",
       "4      1000588         Joni  P00057942      M     26-35   28       1   \n",
       "...        ...          ...        ...    ...       ...  ...     ...   \n",
       "11246  1000695      Manning  P00296942      M     18-25   19       1   \n",
       "11247  1004089  Reichenbach  P00171342      M     26-35   33       0   \n",
       "11248  1001209        Oshin  P00201342      F     36-45   40       0   \n",
       "11249  1004023       Noonan  P00059442      M     36-45   37       0   \n",
       "11250  1002744      Brumley  P00281742      F     18-25   19       0   \n",
       "\n",
       "                State      Zone       Occupation Product_Category  Orders  \\\n",
       "0         Maharashtra   Western       Healthcare             Auto       1   \n",
       "1      Andhra Pradesh  Southern             Govt             Auto       3   \n",
       "2       Uttar Pradesh   Central       Automobile             Auto       3   \n",
       "3           Karnataka  Southern     Construction             Auto       2   \n",
       "4             Gujarat   Western  Food Processing             Auto       2   \n",
       "...               ...       ...              ...              ...     ...   \n",
       "11246     Maharashtra   Western         Chemical           Office       4   \n",
       "11247         Haryana  Northern       Healthcare       Veterinary       3   \n",
       "11248  Madhya Pradesh   Central          Textile           Office       4   \n",
       "11249       Karnataka  Southern      Agriculture           Office       3   \n",
       "11250     Maharashtra   Western       Healthcare           Office       3   \n",
       "\n",
       "       Amount  \n",
       "0       23952  \n",
       "1       23934  \n",
       "2       23924  \n",
       "3       23912  \n",
       "4       23877  \n",
       "...       ...  \n",
       "11246     370  \n",
       "11247     367  \n",
       "11248     213  \n",
       "11249     206  \n",
       "11250     188  \n",
       "\n",
       "[11239 rows x 13 columns]"
      ]
     },
     "execution_count": 18,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# Rename column\n",
    "df.rename(columns={\"Marital_Status\":\"Shaadi\"})"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 19,
   "id": "ad944c91",
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
       "      <th>User_ID</th>\n",
       "      <th>Age</th>\n",
       "      <th>Marital_Status</th>\n",
       "      <th>Orders</th>\n",
       "      <th>Amount</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>count</th>\n",
       "      <td>1.123900e+04</td>\n",
       "      <td>11239.000000</td>\n",
       "      <td>11239.000000</td>\n",
       "      <td>11239.000000</td>\n",
       "      <td>11239.000000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>mean</th>\n",
       "      <td>1.003004e+06</td>\n",
       "      <td>35.410357</td>\n",
       "      <td>0.420055</td>\n",
       "      <td>2.489634</td>\n",
       "      <td>9453.610553</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>std</th>\n",
       "      <td>1.716039e+03</td>\n",
       "      <td>12.753866</td>\n",
       "      <td>0.493589</td>\n",
       "      <td>1.114967</td>\n",
       "      <td>5222.355168</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>min</th>\n",
       "      <td>1.000001e+06</td>\n",
       "      <td>12.000000</td>\n",
       "      <td>0.000000</td>\n",
       "      <td>1.000000</td>\n",
       "      <td>188.000000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>25%</th>\n",
       "      <td>1.001492e+06</td>\n",
       "      <td>27.000000</td>\n",
       "      <td>0.000000</td>\n",
       "      <td>2.000000</td>\n",
       "      <td>5443.000000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>50%</th>\n",
       "      <td>1.003064e+06</td>\n",
       "      <td>33.000000</td>\n",
       "      <td>0.000000</td>\n",
       "      <td>2.000000</td>\n",
       "      <td>8109.000000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>75%</th>\n",
       "      <td>1.004426e+06</td>\n",
       "      <td>43.000000</td>\n",
       "      <td>1.000000</td>\n",
       "      <td>3.000000</td>\n",
       "      <td>12675.000000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>max</th>\n",
       "      <td>1.006040e+06</td>\n",
       "      <td>92.000000</td>\n",
       "      <td>1.000000</td>\n",
       "      <td>4.000000</td>\n",
       "      <td>23952.000000</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "            User_ID           Age  Marital_Status        Orders        Amount\n",
       "count  1.123900e+04  11239.000000    11239.000000  11239.000000  11239.000000\n",
       "mean   1.003004e+06     35.410357        0.420055      2.489634   9453.610553\n",
       "std    1.716039e+03     12.753866        0.493589      1.114967   5222.355168\n",
       "min    1.000001e+06     12.000000        0.000000      1.000000    188.000000\n",
       "25%    1.001492e+06     27.000000        0.000000      2.000000   5443.000000\n",
       "50%    1.003064e+06     33.000000        0.000000      2.000000   8109.000000\n",
       "75%    1.004426e+06     43.000000        1.000000      3.000000  12675.000000\n",
       "max    1.006040e+06     92.000000        1.000000      4.000000  23952.000000"
      ]
     },
     "execution_count": 19,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# Describe the data in dataFrame\n",
    "df.describe()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 20,
   "id": "24227b0b",
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
       "      <th>Age</th>\n",
       "      <th>Orders</th>\n",
       "      <th>Amount</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>count</th>\n",
       "      <td>11239.000000</td>\n",
       "      <td>11239.000000</td>\n",
       "      <td>11239.000000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>mean</th>\n",
       "      <td>35.410357</td>\n",
       "      <td>2.489634</td>\n",
       "      <td>9453.610553</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>std</th>\n",
       "      <td>12.753866</td>\n",
       "      <td>1.114967</td>\n",
       "      <td>5222.355168</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>min</th>\n",
       "      <td>12.000000</td>\n",
       "      <td>1.000000</td>\n",
       "      <td>188.000000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>25%</th>\n",
       "      <td>27.000000</td>\n",
       "      <td>2.000000</td>\n",
       "      <td>5443.000000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>50%</th>\n",
       "      <td>33.000000</td>\n",
       "      <td>2.000000</td>\n",
       "      <td>8109.000000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>75%</th>\n",
       "      <td>43.000000</td>\n",
       "      <td>3.000000</td>\n",
       "      <td>12675.000000</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>max</th>\n",
       "      <td>92.000000</td>\n",
       "      <td>4.000000</td>\n",
       "      <td>23952.000000</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "                Age        Orders        Amount\n",
       "count  11239.000000  11239.000000  11239.000000\n",
       "mean      35.410357      2.489634   9453.610553\n",
       "std       12.753866      1.114967   5222.355168\n",
       "min       12.000000      1.000000    188.000000\n",
       "25%       27.000000      2.000000   5443.000000\n",
       "50%       33.000000      2.000000   8109.000000\n",
       "75%       43.000000      3.000000  12675.000000\n",
       "max       92.000000      4.000000  23952.000000"
      ]
     },
     "execution_count": 20,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# Describe for specific columns\n",
    "df[[\"Age\",\"Orders\",\"Amount\"]].describe()"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "d9d7fb32",
   "metadata": {},
   "source": [
    "# Exploratory Data Analysis"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 21,
   "id": "53f453c2",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": 
       "<Figure size 640x480 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "# Plotting bar chart for Gender\n",
    "ax=sns.countplot(x=\"Gender\",data=df)\n",
    "\n",
    "for bars in ax.containers:\n",
    "    ax.bar_label(bars)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 23,
   "id": "6d429547",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "<AxesSubplot:xlabel='Gender', ylabel='Amount'>"
      ]
     },
     "execution_count": 23,
     "metadata": {},
     "output_type": "execute_result"
    },
    {
     "data"
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "# plotting a bar chart for Gender vs Total Amount\n",
    "sales_gen=df.groupby([\"Gender\"],as_index=False)[\"Amount\"].sum().sort_values(by=\"Amount\",ascending=False)\n",
    "sns.barplot(x=\"Gender\",y=\"Amount\",data=sales_gen)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "50545a2c",
   "metadata": {},
   "source": [
    "# Age"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 24,
   "id": "2fc99e44",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": 
       "<Figure size 640x480 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "ax=sns.countplot(data=df,x=\"Age Group\",hue=\"Gender\")\n",
    "\n",
    "for bars in ax.containers:\n",
    "    ax.bar_label(bars)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 26,
   "id": "985c2523",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "<AxesSubplot:xlabel='Age Group', ylabel='Amount'>"
      ]
     },
     "execution_count": 26,
     "metadata": {},
     "output_type": "execute_result"
    },
    {
     "data": {
      "image/png": 
   "source": [
    "# Total Amount vs Age Group\n",
    "sales_age=df.groupby([\"Age Group\"],as_index=False)[\"Amount\"].sum().sort_values(by=\"Amount\",ascending=False)\n",
    "sns.barplot(x=\"Age Group\",y=\"Amount\",data=sales_age)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "5bb13919",
   "metadata": {},
   "source": [
    "# State"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 34,
   "id": "90a7e3c1",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "<AxesSubplot:xlabel='State', ylabel='Orders'>"
      ]
     },
     "execution_count": 34,
     "metadata": {},
     "output_type": "execute_result"
    },
    
   "source": [
    "sales_state=df.groupby([\"State\"],as_index=False)[\"Orders\"].sum().sort_values(by=\"Orders\",ascending=False).head(10)\n",
    "sns.set(rc={\"figure.figsize\":(15,5)})\n",
    "sns.barplot(x=\"State\",y=\"Orders\",data=sales_state)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 35,
   "id": "85a1bea7",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "<AxesSubplot:xlabel='State', ylabel='Amount'>"
      ]
     },
     "execution_count": 35,
     "metadata": {},
     "output_type": "execute_result"
    },
    
   "source": [
    "#Total Amount/Sales from top 10 States\n",
    "sales_state=df.groupby([\"State\"],as_index=False)[\"Amount\"].sum().sort_values(by=\"Amount\",ascending=False).head(10)\n",
    "sns.set(rc={\"figure.figsize\":(15,5)})\n",
    "sns.barplot(x=\"State\",y=\"Amount\",data=sales_state)Occupation"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "73ad2962",
   "metadata": {},
   "source": [
    "# Marital Status"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 36,
   "id": "f599b4e4",
   "metadata": {},
   "outputs": [
    {
     "data": 
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "ax=sns.countplot(x=\"Marital_Status\",data=df)\n",
    "sns.set(rc={\"figure.figsize\":(7,5)})\n",
    "for bars in ax.containers:\n",
    "    ax.bar_label(bars)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 37,
   "id": "77728022",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "<AxesSubplot:xlabel='Marital_Status', ylabel='Amount'>"
      ]
     },
     "execution_count": 37,
     "metadata": {},
     "output_type": "execute_result"
    },
    {
     "data": {
      "image/png": 
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "sales_state=df.groupby([\"Marital_Status\",\"Gender\"],as_index=False)[\"Amount\"].sum().sort_values(by=\"Amount\",ascending=False)\n",
    "sns.set(rc={\"figure.figsize\":(6,5)})\n",
    "sns.barplot(x=\"Marital_Status\",y=\"Amount\",data=sales_state,hue=\"Gender\")"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "46dff27c",
   "metadata": {},
   "source": [
    "# Occupation"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 39,
   "id": "30189196",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": 
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "ax=sns.countplot(x=\"Occupation\",data=df)\n",
    "sns.set(rc={\"figure.figsize\":(20,5)})\n",
    "for bars in ax.containers:\n",
    "    ax.bar_label(bars)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 41,
   "id": "7927b5d1",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "<AxesSubplot:xlabel='Occupation', ylabel='Amount'>"
      ]
     },
     "execution_count": 41,
     "metadata": {},
     "output_type": "execute_result"
    },
    {
     "data": {
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "sales_state=df.groupby([\"Occupation\"],as_index=False)[\"Amount\"].sum().sort_values(by=\"Amount\",ascending=False)\n",
    "sns.set(rc={\"figure.figsize\":(20,5)})\n",
    "sns.barplot(x=\"Occupation\",y=\"Amount\",data=sales_state)"
   ]
  },
  {
   "cell_type": "markdown",
   "id": "524a46f9",
   "metadata": {},
   "source": [
    "# Product Category"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 46,
   "id": "8217110c",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": 
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "ax=sns.countplot(x=\"Product_Category\",data=df)\n",
    "sns.set(rc={\"figure.figsize\":(20,5)})\n",
    "for bars in ax.containers:\n",
    "    ax.bar_label(bars)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 47,
   "id": "81e69a1c",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "<AxesSubplot:xlabel='Product_Category', ylabel='Amount'>"
      ]
     },
     "execution_count": 47,
     "metadata": {},
     "output_type": "execute_result"
    },
    
   "source": [
    "sales_state=df.groupby([\"Product_Category\"],as_index=False)[\"Amount\"].sum().sort_values(by=\"Amount\",ascending=False).head(10)\n",
    "sns.set(rc={\"figure.figsize\":(20,5)})\n",
    "sns.barplot(x=\"Product_Category\",y=\"Amount\",data=sales_state)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 49,
   "id": "fe8165d9",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "<AxesSubplot:xlabel='Product_ID', ylabel='Orders'>"
      ]
     },
     "execution_count": 49,
     "metadata": {},
     "output_type": "execute_result"
    },
    
   "source": [
    "# Top 10 most sold products\n",
    "sales_state=df.groupby([\"Product_ID\"],as_index=False)[\"Orders\"].sum().sort_values(by=\"Orders\",ascending=False).head(10)\n",
    "sns.set(rc={\"figure.figsize\":(20,5)})\n",
    "sns.barplot(x=\"Product_ID\",y=\"Orders\",data=sales_state)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 50,
   "id": "26db3854",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "<AxesSubplot:xlabel='Product_ID'>"
      ]
     },
     "execution_count": 50,
     "metadata": {},
     "output_type": "execute_result"
    },
    {
     "data": {
      "image/png": 
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "# Top 10 most sold products\n",
    "fig1,ax1=plt.subplots(figsize=(12,7))\n",
    "df.groupby(\"Product_ID\")[\"Orders\"].sum().nlargest(10).sort_values(ascending=False).plot(kind=\"bar\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "id": "3d5a5c34",
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
   "version": "3.9.13"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}

