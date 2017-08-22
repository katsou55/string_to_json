{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 1,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "def string_to_dict(record):\n",
    "    \"\"\"Works as long there no spaces between elements/records\"\"\"\n",
    "    \n",
    "    import re\n",
    "    \n",
    "    rec = '{\"' +  re.sub('\\s+', '\"', record.strip().replace('\\n', '\",\"')).replace('=', ':') + '\"}'\n",
    "    return eval(rec)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 2,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "def string_to_json(record):\n",
    "    \"\"\"Works as long there no spaces between elements/records\"\"\"\n",
    "    \n",
    "    import re\n",
    "    import json\n",
    "    \n",
    "    rec = '{\"' +  re.sub('\\s+', '\"', record.strip().replace('\\n', '\",\"')).replace('=', ':') + '\"}'\n",
    "    return json.dumps(eval(rec))"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "example_1 = \"\"\"A = yes\n",
    "B = true\n",
    "C = 12.34\n",
    "D = 92.34\"\"\""
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 4,
   "metadata": {
    "collapsed": true
   },
   "outputs": [],
   "source": [
    "example_2 = \"\"\"\n",
    "\n",
    "A = yes\n",
    "B = true\n",
    "C = 12.34\n",
    "D = 92.34\n",
    "\n",
    "\"\"\""
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 5,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "{'A': 'yes', 'B': 'true', 'C': '12.34', 'D': '92.34'}"
      ]
     },
     "execution_count": 5,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "string_to_dict(example_1)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 6,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "{'A': 'yes', 'B': 'true', 'C': '12.34', 'D': '92.34'}"
      ]
     },
     "execution_count": 6,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "string_to_dict(example_2)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 7,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "'{\"A\": \"yes\", \"C\": \"12.34\", \"B\": \"true\", \"D\": \"92.34\"}'"
      ]
     },
     "execution_count": 7,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "string_to_json(example_1)"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 8,
   "metadata": {
    "collapsed": false
   },
   "outputs": [
    {
     "data": {
      "text/plain": [
       "'{\"A\": \"yes\", \"C\": \"12.34\", \"B\": \"true\", \"D\": \"92.34\"}'"
      ]
     },
     "execution_count": 8,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "string_to_json(example_2)"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python [testenv]",
   "language": "python",
   "name": "Python [testenv]"
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
   "version": "2.7.13"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 0
}
