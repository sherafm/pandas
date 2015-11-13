{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "### Data Source"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1249,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": [
    "import data\n",
    "\n",
    "critics = data.critics"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "### Ratings \n",
    "\n",
    "\n",
    "The dictionary is transformed into a DataFrame and axes are swaped for a better overview of the Dataset"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1250,
   "metadata": {
    "collapsed": false,
    "scrolled": false
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>Just My Luck</th>\n",
       "      <th>Lady in the Water</th>\n",
       "      <th>Snakes on a Plane</th>\n",
       "      <th>Superman Returns</th>\n",
       "      <th>The Night Listener</th>\n",
       "      <th>You, Me and Dupree</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>Claudia Puig</th>\n",
       "      <td>3.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>3.5</td>\n",
       "      <td>4.0</td>\n",
       "      <td>4.5</td>\n",
       "      <td>2.5</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>Gene Seymour</th>\n",
       "      <td>1.5</td>\n",
       "      <td>3.0</td>\n",
       "      <td>3.5</td>\n",
       "      <td>5.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>3.5</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>Jack Matthews</th>\n",
       "      <td>NaN</td>\n",
       "      <td>3.0</td>\n",
       "      <td>4.0</td>\n",
       "      <td>5.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>3.5</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>Lisa Rose</th>\n",
       "      <td>3.0</td>\n",
       "      <td>2.5</td>\n",
       "      <td>3.5</td>\n",
       "      <td>3.5</td>\n",
       "      <td>3.0</td>\n",
       "      <td>2.5</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>Michael Phillips</th>\n",
       "      <td>NaN</td>\n",
       "      <td>2.5</td>\n",
       "      <td>3.0</td>\n",
       "      <td>3.5</td>\n",
       "      <td>4.0</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>Mick LaSalle</th>\n",
       "      <td>2.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>4.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>2.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>Toby</th>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>4.5</td>\n",
       "      <td>4.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>1.0</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "                  Just My Luck  Lady in the Water  Snakes on a Plane  \\\n",
       "Claudia Puig               3.0                NaN                3.5   \n",
       "Gene Seymour               1.5                3.0                3.5   \n",
       "Jack Matthews              NaN                3.0                4.0   \n",
       "Lisa Rose                  3.0                2.5                3.5   \n",
       "Michael Phillips           NaN                2.5                3.0   \n",
       "Mick LaSalle               2.0                3.0                4.0   \n",
       "Toby                       NaN                NaN                4.5   \n",
       "\n",
       "                  Superman Returns  The Night Listener  You, Me and Dupree  \n",
       "Claudia Puig                   4.0                 4.5                 2.5  \n",
       "Gene Seymour                   5.0                 3.0                 3.5  \n",
       "Jack Matthews                  5.0                 3.0                 3.5  \n",
       "Lisa Rose                      3.5                 3.0                 2.5  \n",
       "Michael Phillips               3.5                 4.0                 NaN  \n",
       "Mick LaSalle                   3.0                 3.0                 2.0  \n",
       "Toby                           4.0                 NaN                 1.0  "
      ]
     },
     "execution_count": 1250,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "import pandas as pd\n",
    "import numpy as np\n",
    "import math\n",
    "\n",
    "\n",
    "ratings = pd.DataFrame(critics)\n",
    "\n",
    "ratings.swapaxes(0,1)"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "\n",
    "\n",
    "\n",
    "\n",
    "\n",
    "\n",
    "\n",
    "# Exercice 1\n",
    "\n",
    "## 1) Similarity\n",
    "\n",
    "\n",
    "Similarity Scores can be calculated from the sum of distances between two critics' ratings:\n"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1251,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "3.0"
      ]
     },
     "execution_count": 1251,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# Claudia's Rating Of \"Just My Luck\"\n",
    "\n",
    "critics[\"Claudia Puig\"][\"Just My Luck\"]"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1252,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "1.5"
      ]
     },
     "execution_count": 1252,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# The \"Distance\" Between Claudia And Gene's Ratings For The Movie \"Just My Luck\"\n",
    "\n",
    "abs(critics[\"Claudia Puig\"][\"Just My Luck\"]\n",
    "    - \n",
    "    critics[\"Gene Seymour\"][\"Just My Luck\"])\n",
    "\n",
    "# The Larger The Distance Is, The Less Similar Their Ratings Are"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1253,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": [
    "# The Function Evaluating The Taste Similarity Between Two Persons:\n",
    "\n",
    "def similarity(prefs, person1, person2):\n",
    "    \n",
    "    movies =[ x for y in prefs.itervalues() for x in y.iterkeys()]\n",
    "    movies = set(movies) # Getting Unique Movies Names From The Dictionary\n",
    "    score = 0 # Score Initialization\n",
    "    \n",
    "    for movie in movies: # Iteration Of The Movies Listed Above To Sum The Distances\n",
    "        try:\n",
    "            score = score + (abs(prefs[person1][movie]\n",
    "                            - prefs[person2][movie]))\n",
    "            \n",
    "        except KeyError:  # To Avoid \"NaN\" Values\n",
    "            pass\n",
    "    \n",
    "    ratings = pd.DataFrame(prefs)\n",
    "\n",
    "    return round(score/(len(movies)*5),2)\n",
    "    # The Sum Of Diffences Is Divided By The Largest Difference Possible\n",
    "    # i.e. The DataFrame's Width (The Number Of Movies)\n",
    "\n",
    "# The Lower The Score Is, The More Similar Their Tastes Are"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1254,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "0.17"
      ]
     },
     "execution_count": 1254,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# Example 1\n",
    "\n",
    "similarity(critics, \"Claudia Puig\", \"Gene Seymour\")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1255,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "0.02"
      ]
     },
     "execution_count": 1255,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# Example 2 - In This One, The Two Critics Are Much Closer\n",
    "\n",
    "similarity(critics, \"Gene Seymour\", \"Jack Matthews\")"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {
    "collapsed": true
   },
   "source": [
    "## 2) Ranking"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1256,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": [
    "# The Function To Rank The n Closest Critics\n",
    "\n",
    "\n",
    "def top_matches(prefs, person, n=5):\n",
    "\n",
    "    reviewers = critics.keys() # Creation Of A Reviewer List For The Function\n",
    "    \n",
    "    ranking = [] # List initialization\n",
    "    \n",
    "    for reviewer in reviewers:\n",
    "        \n",
    "        if reviewer != person: # Condition To Not Self-Compare The Critic\n",
    "            \n",
    "            # Calling The Scoring Function Previously Created\n",
    "            ranking.append((similarity(prefs, person, reviewer), reviewer)) # Score(float) + Critic(str)\n",
    "            \n",
    "    ranking.sort() # Sort The Tuple List To Rank The Critics\n",
    "    \n",
    "    return ranking[:n] # To Return The n Critics With The Highest Scores"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1257,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "[(0.07, 'Michael Phillips'),\n",
       " (0.08, 'Claudia Puig'),\n",
       " (0.08, 'Mick LaSalle'),\n",
       " (0.1, 'Lisa Rose'),\n",
       " (0.13, 'Jack Matthews')]"
      ]
     },
     "execution_count": 1257,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "top_matches(critics, \"Toby\", n=5)\n",
    "\n",
    "# Michael's Ratings Are The Closest To Toby's"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "# Exercise 2 - Recommendation\n",
    "\n",
    "\n",
    "To recommend movies to Toby, the recommendation algorithm has to weighten movie critics according to their Similarity Score. The closer the critic is, the more he will influence the recommendation."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1258,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": [
    "# Calculation Of Similarity Scores For Toby\n",
    "\n",
    "Top_Toby = top_matches(critics, \"Toby\", n=len(reviewers))"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1259,
   "metadata": {
    "collapsed": false,
    "scrolled": true
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>Similarity</th>\n",
       "      <th>Names</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>0.07</td>\n",
       "      <td>Michael Phillips</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>0.08</td>\n",
       "      <td>Claudia Puig</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>0.08</td>\n",
       "      <td>Mick LaSalle</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>0.10</td>\n",
       "      <td>Lisa Rose</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>0.13</td>\n",
       "      <td>Jack Matthews</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>5</th>\n",
       "      <td>0.15</td>\n",
       "      <td>Gene Seymour</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "   Similarity             Names\n",
       "0        0.07  Michael Phillips\n",
       "1        0.08      Claudia Puig\n",
       "2        0.08      Mick LaSalle\n",
       "3        0.10         Lisa Rose\n",
       "4        0.13     Jack Matthews\n",
       "5        0.15      Gene Seymour"
      ]
     },
     "execution_count": 1259,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# Similarity Scores Calculated Above Are Transformed Into A Pandas DataFrame\n",
    "# Names Have To Be Labeled The Same Way As The Ratings DataFrame To Merge Both DFs.\n",
    "\n",
    "Coef = pd.DataFrame(Top_Toby)\n",
    "\n",
    "Coef.columns = ['Similarity', 'Names']\n",
    "\n",
    "\n",
    "Coef"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1260,
   "metadata": {
    "collapsed": false,
    "scrolled": false
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>Names</th>\n",
       "      <th>Just My Luck</th>\n",
       "      <th>Lady in the Water</th>\n",
       "      <th>Snakes on a Plane</th>\n",
       "      <th>Superman Returns</th>\n",
       "      <th>The Night Listener</th>\n",
       "      <th>You, Me and Dupree</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>Claudia Puig</td>\n",
       "      <td>3.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>3.5</td>\n",
       "      <td>4.0</td>\n",
       "      <td>4.5</td>\n",
       "      <td>2.5</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>Gene Seymour</td>\n",
       "      <td>1.5</td>\n",
       "      <td>3.0</td>\n",
       "      <td>3.5</td>\n",
       "      <td>5.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>3.5</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>Jack Matthews</td>\n",
       "      <td>NaN</td>\n",
       "      <td>3.0</td>\n",
       "      <td>4.0</td>\n",
       "      <td>5.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>3.5</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>Lisa Rose</td>\n",
       "      <td>3.0</td>\n",
       "      <td>2.5</td>\n",
       "      <td>3.5</td>\n",
       "      <td>3.5</td>\n",
       "      <td>3.0</td>\n",
       "      <td>2.5</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>Michael Phillips</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2.5</td>\n",
       "      <td>3.0</td>\n",
       "      <td>3.5</td>\n",
       "      <td>4.0</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>5</th>\n",
       "      <td>Mick LaSalle</td>\n",
       "      <td>2.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>4.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>2.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>6</th>\n",
       "      <td>Toby</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>4.5</td>\n",
       "      <td>4.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>1.0</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "              Names  Just My Luck  Lady in the Water  Snakes on a Plane  \\\n",
       "0      Claudia Puig           3.0                NaN                3.5   \n",
       "1      Gene Seymour           1.5                3.0                3.5   \n",
       "2     Jack Matthews           NaN                3.0                4.0   \n",
       "3         Lisa Rose           3.0                2.5                3.5   \n",
       "4  Michael Phillips           NaN                2.5                3.0   \n",
       "5      Mick LaSalle           2.0                3.0                4.0   \n",
       "6              Toby           NaN                NaN                4.5   \n",
       "\n",
       "   Superman Returns  The Night Listener  You, Me and Dupree  \n",
       "0               4.0                 4.5                 2.5  \n",
       "1               5.0                 3.0                 3.5  \n",
       "2               5.0                 3.0                 3.5  \n",
       "3               3.5                 3.0                 2.5  \n",
       "4               3.5                 4.0                 NaN  \n",
       "5               3.0                 3.0                 2.0  \n",
       "6               4.0                 NaN                 1.0  "
      ]
     },
     "execution_count": 1260,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# The Rating DataFrame And The Similarity Scores Have To Be Merged Through Critics Names\n",
    "\n",
    "\n",
    "ratings = ratings.swapaxes(1,0)\n",
    "\n",
    "ratings.reset_index(level=0, inplace=True) \n",
    "\n",
    "ratings.columns = ratings.columns.str.replace('index','Names')\n",
    "\n",
    "# Names Are Vertically Sorted And Taken Out Of The Index Column, and Renamed.\n",
    "# The Dfs Are Ready To Merge\n",
    "\n",
    "ratings"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1261,
   "metadata": {
    "collapsed": false,
    "scrolled": false
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>Similarity</th>\n",
       "      <th>Names</th>\n",
       "      <th>Just My Luck</th>\n",
       "      <th>Lady in the Water</th>\n",
       "      <th>Snakes on a Plane</th>\n",
       "      <th>Superman Returns</th>\n",
       "      <th>The Night Listener</th>\n",
       "      <th>You, Me and Dupree</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>0.07</td>\n",
       "      <td>Michael Phillips</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2.5</td>\n",
       "      <td>3.0</td>\n",
       "      <td>3.5</td>\n",
       "      <td>4.0</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>0.08</td>\n",
       "      <td>Claudia Puig</td>\n",
       "      <td>3.0</td>\n",
       "      <td>NaN</td>\n",
       "      <td>3.5</td>\n",
       "      <td>4.0</td>\n",
       "      <td>4.5</td>\n",
       "      <td>2.5</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>0.08</td>\n",
       "      <td>Mick LaSalle</td>\n",
       "      <td>2.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>4.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>2.0</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>0.10</td>\n",
       "      <td>Lisa Rose</td>\n",
       "      <td>3.0</td>\n",
       "      <td>2.5</td>\n",
       "      <td>3.5</td>\n",
       "      <td>3.5</td>\n",
       "      <td>3.0</td>\n",
       "      <td>2.5</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>0.13</td>\n",
       "      <td>Jack Matthews</td>\n",
       "      <td>NaN</td>\n",
       "      <td>3.0</td>\n",
       "      <td>4.0</td>\n",
       "      <td>5.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>3.5</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>5</th>\n",
       "      <td>0.15</td>\n",
       "      <td>Gene Seymour</td>\n",
       "      <td>1.5</td>\n",
       "      <td>3.0</td>\n",
       "      <td>3.5</td>\n",
       "      <td>5.0</td>\n",
       "      <td>3.0</td>\n",
       "      <td>3.5</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "   Similarity             Names  Just My Luck  Lady in the Water  \\\n",
       "0        0.07  Michael Phillips           NaN                2.5   \n",
       "1        0.08      Claudia Puig           3.0                NaN   \n",
       "2        0.08      Mick LaSalle           2.0                3.0   \n",
       "3        0.10         Lisa Rose           3.0                2.5   \n",
       "4        0.13     Jack Matthews           NaN                3.0   \n",
       "5        0.15      Gene Seymour           1.5                3.0   \n",
       "\n",
       "   Snakes on a Plane  Superman Returns  The Night Listener  You, Me and Dupree  \n",
       "0                3.0               3.5                 4.0                 NaN  \n",
       "1                3.5               4.0                 4.5                 2.5  \n",
       "2                4.0               3.0                 3.0                 2.0  \n",
       "3                3.5               3.5                 3.0                 2.5  \n",
       "4                4.0               5.0                 3.0                 3.5  \n",
       "5                3.5               5.0                 3.0                 3.5  "
      ]
     },
     "execution_count": 1261,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "result = pd.merge(Coef, ratings, on='Names')\n",
    "\n",
    "result"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1262,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>Similarity</th>\n",
       "      <th>Names</th>\n",
       "      <th>Just My Luck</th>\n",
       "      <th>Lady in the Water</th>\n",
       "      <th>Snakes on a Plane</th>\n",
       "      <th>Superman Returns</th>\n",
       "      <th>The Night Listener</th>\n",
       "      <th>You, Me and Dupree</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>0.07</td>\n",
       "      <td>Michael Phillips</td>\n",
       "      <td>NaN</td>\n",
       "      <td>35.71</td>\n",
       "      <td>42.86</td>\n",
       "      <td>50</td>\n",
       "      <td>57.14</td>\n",
       "      <td>NaN</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>0.08</td>\n",
       "      <td>Claudia Puig</td>\n",
       "      <td>37.5</td>\n",
       "      <td>NaN</td>\n",
       "      <td>43.75</td>\n",
       "      <td>50</td>\n",
       "      <td>56.25</td>\n",
       "      <td>31.25</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>0.08</td>\n",
       "      <td>Mick LaSalle</td>\n",
       "      <td>25</td>\n",
       "      <td>37.5</td>\n",
       "      <td>50</td>\n",
       "      <td>37.5</td>\n",
       "      <td>37.5</td>\n",
       "      <td>25</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>0.1</td>\n",
       "      <td>Lisa Rose</td>\n",
       "      <td>30</td>\n",
       "      <td>25</td>\n",
       "      <td>35</td>\n",
       "      <td>35</td>\n",
       "      <td>30</td>\n",
       "      <td>25</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>0.13</td>\n",
       "      <td>Jack Matthews</td>\n",
       "      <td>NaN</td>\n",
       "      <td>23.08</td>\n",
       "      <td>30.77</td>\n",
       "      <td>38.46</td>\n",
       "      <td>23.08</td>\n",
       "      <td>26.92</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>5</th>\n",
       "      <td>0.15</td>\n",
       "      <td>Gene Seymour</td>\n",
       "      <td>10</td>\n",
       "      <td>20</td>\n",
       "      <td>23.33</td>\n",
       "      <td>33.33</td>\n",
       "      <td>20</td>\n",
       "      <td>23.33</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>Score</th>\n",
       "      <td></td>\n",
       "      <td></td>\n",
       "      <td>102.5</td>\n",
       "      <td>141.29</td>\n",
       "      <td>225.71</td>\n",
       "      <td>244.29</td>\n",
       "      <td>223.97</td>\n",
       "      <td>131.5</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "</div>"
      ],
      "text/plain": [
       "      Similarity             Names Just My Luck Lady in the Water  \\\n",
       "0           0.07  Michael Phillips          NaN             35.71   \n",
       "1           0.08      Claudia Puig         37.5               NaN   \n",
       "2           0.08      Mick LaSalle           25              37.5   \n",
       "3            0.1         Lisa Rose           30                25   \n",
       "4           0.13     Jack Matthews          NaN             23.08   \n",
       "5           0.15      Gene Seymour           10                20   \n",
       "Score                                     102.5            141.29   \n",
       "\n",
       "      Snakes on a Plane Superman Returns The Night Listener You, Me and Dupree  \n",
       "0                 42.86               50              57.14                NaN  \n",
       "1                 43.75               50              56.25              31.25  \n",
       "2                    50             37.5               37.5                 25  \n",
       "3                    35               35                 30                 25  \n",
       "4                 30.77            38.46              23.08              26.92  \n",
       "5                 23.33            33.33                 20              23.33  \n",
       "Score            225.71           244.29             223.97              131.5  "
      ]
     },
     "execution_count": 1262,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# A Loop Is Created To Weighten The Movie Ratings According To The Similarity Score\n",
    "\n",
    "for n in range(2,8):\n",
    "    result[result.columns[n]] = (1/result['Similarity'])*result[result.columns[n]]\n",
    "    # The Inverse Function Is Needed To Accurately Use The Similarity Scores\n",
    "\n",
    "numeric = result.select_dtypes(include=[np.number])\n",
    "result.loc[:, numeric.columns] = np.round(numeric,2) # Numerical Values Are Rounded For A Better Overview\n",
    "\n",
    "result = result.swapaxes(1,0)\n",
    "\n",
    "result['Score'] = result.sum(axis=1) # A \"Score\" Row Is Added At The Bottom\n",
    "\n",
    "result = result.swapaxes(1,0)\n",
    "\n",
    "result[\"Similarity\"][6]=\"\" # DataFrame Cleaning\n",
    "result[\"Names\"][6]=\"\"\n",
    "    \n",
    "result"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1263,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "[(223.97, 'The Night Listener'),\n",
       " (141.29, 'Lady in the Water'),\n",
       " (102.5, 'Just My Luck')]"
      ]
     },
     "execution_count": 1263,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "Top = []\n",
    "    \n",
    "for movie in movies:\n",
    "    if math.isnan(ratings.loc[ratings['Names'] == \"Toby\"][movie].item()) == True :\n",
    "        Top.append((round(result.iloc[-1,2:][movie],2), movie))\n",
    "\n",
    "Top.sort(reverse=True)\n",
    "\n",
    "Top"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1245,
   "metadata": {
    "collapsed": false
   },
   "outputs": [],
   "source": [
    "# The Whole Process Can Be Sumed Up In This Recommendation Function:\n",
    "\n",
    "def get_recommendations(prefs, person):\n",
    "    \n",
    "    # Similarity DF\n",
    "    \n",
    "    Coef = pd.DataFrame(top_matches(prefs, person, n=6))\n",
    "    Coef.columns = ['Similarity', 'Names']\n",
    "    \n",
    "    \n",
    "    # Ratings DF\n",
    "    \n",
    "    ratings = pd.DataFrame(prefs).swapaxes(1,0)\n",
    "    ratings.reset_index(level=0, inplace=True) \n",
    "    ratings.columns = ratings.columns.str.replace('index','Names')\n",
    "    \n",
    "    \n",
    "    # DFs Merger\n",
    "    \n",
    "    result = pd.merge(Coef, ratings, on='Names')\n",
    "    \n",
    "    \n",
    "    # Ratings Are Weightened And Rounded\n",
    "    \n",
    "    for n in range(2,8):\n",
    "        result[result.columns[n]] = (1/result['Similarity'])*result[result.columns[n]]\n",
    "    numeric = result.select_dtypes(include=[np.number])\n",
    "    result.loc[:, numeric.columns] = np.round(numeric,2)\n",
    "    \n",
    "    \n",
    "    # Total Scores And DF Cleaning\n",
    "    \n",
    "    result = result.swapaxes(1,0)\n",
    "    result['Score'] = result.sum(axis=1)\n",
    "    result = result.swapaxes(1,0)\n",
    "    result[\"Similarity\"][6]=\"\"\n",
    "    result[\"Names\"][6]=\"\"\n",
    "    \n",
    "    \n",
    "    # Algorithm Calculating The Most Recommended Movie To A Specific Critic\n",
    "    \n",
    "    Top = []\n",
    "    \n",
    "    for movie in movies:\n",
    "        if math.isnan(ratings.loc[ratings['Names'] == person][movie].item()) == True :\n",
    "            Top.append((round(result.iloc[-1,2:][movie],2), movie))\n",
    "\n",
    "    \n",
    "    # Tuple List Sorted By Descending Values\n",
    "    \n",
    "    Top.sort(reverse=True)\n",
    "\n",
    "    return Top"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1246,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "[(223.97, 'The Night Listener'),\n",
       " (141.29, 'Lady in the Water'),\n",
       " (102.5, 'Just My Luck')]"
      ]
     },
     "execution_count": 1246,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# Example 1\n",
    "\n",
    "get_recommendations(critics, \"Toby\") # The Algorithm Would Recommend \"The Night Listener\" To Toby"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1247,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "[]"
      ]
     },
     "execution_count": 1247,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# Example 2\n",
    "\n",
    "get_recommendations(critics, \"Gene Seymour\")\n",
    "\n",
    "# The Algorithme Wouldn't Recommend Anything To Gene Because He Has Watched All The Available Movies"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 1248,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "[(190.38, 'You, Me and Dupree'), (152.5, 'Just My Luck')]"
      ]
     },
     "execution_count": 1248,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "# Example 3\n",
    "\n",
    "get_recommendations(critics, \"Michael Phillips\")"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "## Alternatives\n",
    "\n",
    "Two types of metrics could be used to establish a similarity score:\n",
    "\n",
    "- User-based metrics: Age group, Homecountry, etc.\n",
    "\n",
    "- Movie-based metrics: Genre, Year, Actors, Directors, etc."
   ]
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 2",
   "language": "python",
   "name": "python2"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 2
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython2",
   "version": "2.7.10"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 0
}
