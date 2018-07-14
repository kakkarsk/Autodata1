# Autodata
{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 1,
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
       "      <th>Cars &amp;model</th>\n",
       "      <th>Mileage</th>\n",
       "      <th>Year manufactured</th>\n",
       "      <th>Distance</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>Chevrolet chevelle malibu</td>\n",
       "      <td>12.0</td>\n",
       "      <td>2010</td>\n",
       "      <td>3504</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>Buick skylark 320</td>\n",
       "      <td>11.5</td>\n",
       "      <td>2013</td>\n",
       "      <td>3693</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>Plymouth satellite</td>\n",
       "      <td>10.0</td>\n",
       "      <td>2006</td>\n",
       "      <td>3436</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>Amc rebel sst</td>\n",
       "      <td>9.0</td>\n",
       "      <td>2008</td>\n",
       "      <td>3433</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>Ford torino</td>\n",
       "      <td>10.0</td>\n",
       "      <td>2011</td>\n",
       "      <td>3449</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "                 Cars &model  Mileage  Year manufactured   Distance\n",
       "0  Chevrolet chevelle malibu     12.0                2010      3504\n",
       "1          Buick skylark 320     11.5                2013      3693\n",
       "2         Plymouth satellite     10.0                2006      3436\n",
       "3              Amc rebel sst      9.0                2008      3433\n",
       "4                Ford torino     10.0                2011      3449"
      ]
     },
     "execution_count": 1,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "import pandas as pd\n",
    "import numpy as np\n",
    "import matplotlib.pyplot as plt\n",
    "%matplotlib inline\n",
    "df =pd.read_csv('autompgdata.csv')\n",
    "df.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 2,
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
       "      <th>Cars &amp;model</th>\n",
       "      <th>Mileage</th>\n",
       "      <th>Year manufactured</th>\n",
       "      <th>Distance</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>11</th>\n",
       "      <td>Plymouth 'cuda 340</td>\n",
       "      <td>13.0</td>\n",
       "      <td>2016</td>\n",
       "      <td>3609</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>12</th>\n",
       "      <td>Chevrolet monte carlo</td>\n",
       "      <td>14.0</td>\n",
       "      <td>2009</td>\n",
       "      <td>3459</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>13</th>\n",
       "      <td>Buick estate wagon (sw)</td>\n",
       "      <td>12.0</td>\n",
       "      <td>2010</td>\n",
       "      <td>4590</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>14</th>\n",
       "      <td>Toyota corona mark ii</td>\n",
       "      <td>11.5</td>\n",
       "      <td>2010</td>\n",
       "      <td>3409</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>15</th>\n",
       "      <td>Plymouth duster</td>\n",
       "      <td>11.0</td>\n",
       "      <td>2017</td>\n",
       "      <td>4569</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "                Cars &model  Mileage  Year manufactured   Distance\n",
       "11       Plymouth 'cuda 340     13.0                2016      3609\n",
       "12    Chevrolet monte carlo     14.0                2009      3459\n",
       "13  Buick estate wagon (sw)     12.0                2010      4590\n",
       "14    Toyota corona mark ii     11.5                2010      3409\n",
       "15          Plymouth duster     11.0                2017      4569"
      ]
     },
     "execution_count": 2,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.tail()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "16"
      ]
     },
     "execution_count": 3,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "len(df)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 4,
   "metadata": {
    "scrolled": true
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "Cars &model            object\n",
       "Mileage               float64\n",
       "Year manufactured       int64\n",
       "Distance                int64\n",
       "dtype: object"
      ]
     },
     "execution_count": 4,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.dtypes"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 5,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": "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\n",
      "text/plain": [
       "<Figure size 432x288 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "import pandas as pd\n",
    "import matplotlib.pyplot as plt\n",
    "%matplotlib inline\n",
    "plt.plot(df['Mileage'],color='green')        \n",
    "plt.xlabel('Mileage')\n",
    "plt.ylabel('Distance')\n",
    "plt.title('Cars&model')\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 6,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": "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\n",
      "text/plain": [
       "<Figure size 432x288 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "import pandas as pd\n",
    "import numpy as np\n",
    "import matplotlib.pyplot as plt\n",
    "%matplotlib inline\n",
    "x =np.random.normal(10,5,100)\n",
    "y =np.random.normal(2,4,50)\n",
    "plt.hist(x,bins=10,color='blue')\n",
    "plt.hist(y,bins=10,color='purple')\n",
    "plt.xlabel('Mileage')\n",
    "plt.ylabel('Distance')\n",
    "plt.title('cars&model')\n",
    "plt.show()\n",
    "        "
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "As per the picture above it shows the data of in the table about Cars hich are manufatured from last 10 to 12 years where it shows about the histogram diagram , where it represents \n",
    "    X as in Mileage \n",
    "    Y as in Distance \n",
    "    And title with cars and model \n",
    "    To show which car has travelled the distance   during in that mileage.\n",
    "   \n",
    "    "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 7,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": "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\n",
      "text/plain": [
       "<Figure size 432x288 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "import pandas as pd\n",
    "import numpy as np\n",
    "import matplotlib.pyplot as plt\n",
    "%matplotlib inline\n",
    "X =np.random.normal(2,3,4)\n",
    "y =np.random.normal(11,13,15)\n",
    "plt.hist(x,bins=10,color=\"orange\")\n",
    "plt.hist(y,bins=10,color=\"black\")\n",
    "plt.xlabel('cars&model')\n",
    "plt.ylabel('Distance')\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "So, in the second histogram picture it is represent which car model have travelled how much distance during last 10 to 12 years.\n",
    "Where as X represent as cars& model\n",
    "and Y represent the histographically the distance \n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 8,
   "metadata": {},
   "outputs": [
    {
     "data": {
      "image/png": "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\n",
      "text/plain": [
       "<Figure size 432x288 with 1 Axes>"
      ]
     },
     "metadata": {},
     "output_type": "display_data"
    }
   ],
   "source": [
    "import pandas as pd\n",
    "import numpy as np\n",
    "import matplotlib.pyplot as plt\n",
    "%matplotlib inline\n",
    "x =np.random.normal(4,5,16)\n",
    "y =np.random.normal(3,6,10)\n",
    "plt.hist(x,bins=20,color=\"red\")\n",
    "plt.hist(y,bins=20,color=\"green\")\n",
    "plt.xlabel('cars&model')\n",
    "plt.ylabel('Year manufactured')\n",
    "plt.show()"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "In this figure it is explained about in which year the Cars model was manufactured , typically showing the histographically the diagram of last 12 years , where y is labelled as Year manufactured and x is cars model\n"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3",
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
   "version": "3.6.5"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 2
}
