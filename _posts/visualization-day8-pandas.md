데이터 시각화
===========
---
title: "day 8"
date: 2020-01-27
categories: blog
---

# 이번 강의는 pandas를 이용한 visualization을 진행한다.
데이터를 처리한 후 seaborn을 이용하여 유용한 시각화의 과정은 거의 대부분 다루었다.
비슷한 시각화를 pandas를 이용하여 해본다. 
사실 pandas는 시각화의 다양한 메소드가 존재하지 않기때문에 기초적인 시각화만이 가능하다.

## colab 첨부
{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "name": "pandas-visualization.ipynb",
      "provenance": [],
      "authorship_tag": "ABX9TyN2rXZ0aIZ4dQFgoZfHDesR",
      "include_colab_link": true
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    }
  },
  "cells": [
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "view-in-github",
        "colab_type": "text"
      },
      "source": [
        "<a href=\"https://colab.research.google.com/github/silverstar0727/1day-1commit-challenge/blob/master/pandas_visualization.ipynb\" target=\"_parent\"><img src=\"https://colab.research.google.com/assets/colab-badge.svg\" alt=\"Open In Colab\"/></a>"
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "g4A8xXU43wxK",
        "colab_type": "text"
      },
      "source": [
        "# histplot"
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "Bjls61l_2CNH",
        "colab_type": "code",
        "outputId": "02a4bee4-94fd-4c3a-f965-c25a57fdb4c9",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 204
        }
      },
      "source": [
        "import pandas as pd\n",
        "import numpy as np\n",
        "import matplotlib.pyplot as plt\n",
        "import matplotlib as mpl\n",
        "\n",
        "mpl.rcParams['axes.unicode_minus'] = False\n",
        "\n",
        "df4 = pd.DataFrame({'a': np.random.randn(1000) +1,\n",
        "                    'b': np.random.randn(1000),\n",
        "                    'c': np.random.randn(1000) -1},\n",
        "                    columns = ['a','b','c'])\n",
        "df4.head()"
      ],
      "execution_count": 0,
      "outputs": [
        {
          "output_type": "execute_result",
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
              "      <th>a</th>\n",
              "      <th>b</th>\n",
              "      <th>c</th>\n",
              "    </tr>\n",
              "  </thead>\n",
              "  <tbody>\n",
              "    <tr>\n",
              "      <th>0</th>\n",
              "      <td>0.565739</td>\n",
              "      <td>-0.845053</td>\n",
              "      <td>-2.160255</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>1</th>\n",
              "      <td>1.799780</td>\n",
              "      <td>-0.569244</td>\n",
              "      <td>-1.928911</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>2</th>\n",
              "      <td>1.969770</td>\n",
              "      <td>-0.992962</td>\n",
              "      <td>-1.009744</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>3</th>\n",
              "      <td>0.699971</td>\n",
              "      <td>-0.509515</td>\n",
              "      <td>-1.769729</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>4</th>\n",
              "      <td>1.157959</td>\n",
              "      <td>0.253632</td>\n",
              "      <td>-0.241176</td>\n",
              "    </tr>\n",
              "  </tbody>\n",
              "</table>\n",
              "</div>"
            ],
            "text/plain": [
              "          a         b         c\n",
              "0  0.565739 -0.845053 -2.160255\n",
              "1  1.799780 -0.569244 -1.928911\n",
              "2  1.969770 -0.992962 -1.009744\n",
              "3  0.699971 -0.509515 -1.769729\n",
              "4  1.157959  0.253632 -0.241176"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 1
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "-H9p6qPa2oOd",
        "colab_type": "code",
        "outputId": "090cfbf8-429f-41cb-ec81-66538406c0f4",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 283
        }
      },
      "source": [
        "df4.plot.hist(alpha = 0.5)"
      ],
      "execution_count": 0,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "<matplotlib.axes._subplots.AxesSubplot at 0x7f2403823a58>"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 3
        },
        {
          "output_type": "display_data",
          "data": {
            "image/png": "iVBORw0KGgoAAAANSUhEUgAAAYUAAAD4CAYAAAAD6PrjAAAABHNCSVQICAgIfAhkiAAAAAlwSFlz\nAAALEgAACxIB0t1+/AAAADh0RVh0U29mdHdhcmUAbWF0cGxvdGxpYiB2ZXJzaW9uMy4xLjIsIGh0\ndHA6Ly9tYXRwbG90bGliLm9yZy8li6FKAAAVdElEQVR4nO3de9RddX3n8ffHkBKpKJdEJpOEhtZI\nCVMBDZRZ2AXiYopoBcdLcRQzyjKO4IzXjreu6oyypl3LimWWwaZKAauleEEZB6YNF6ssQAya4Y5k\nBMkTUdIgIOWige/8cXY2j/QhOUmeffbzPHm/1jrr2fu3L79vDmudD3v/fmefVBWSJAE8o+8CJElT\nh6EgSWoZCpKklqEgSWoZCpKk1m59F7Az5s6dW4sXL+67DEmaVq6//vp/qqp5E22b1qGwePFi1qxZ\n03cZkjStJPnR023z9pEkqWUoSJJahoIkqTWtxxQkqS+//OUvGRsb49FHH+27lKc1Z84cFi5cyOzZ\ns4c+xlCQpB0wNjbGnnvuyeLFi0nSdzn/QlWxadMmxsbGOOCAA4Y+zttHkrQDHn30Ufbdd98pGQgA\nSdh33323+0rGUJCkHTRVA2GLHanPUJAktRxTkKRJcObqH0zq+d593PMn9XzDMhSkGWayP5yG1deH\nmCaXt48kaZo66aSTeNGLXsTBBx/MqlWrJuWcnV0pJJkDfAvYvenny1X1kSTnAkcDDzS7/seqWpvB\niMhfACcADzft3+uqPkma7s455xz22WcfHnnkEQ4//HBe/epXs+++++7UObu8ffQYcGxVPZRkNnBV\nkkubbX9UVV9+yv4vA5Y0r98Fzm7+SpImcNZZZ3HRRRcBsH79eu64446pGwpVVcBDzers5lVbOeRE\n4PzmuGuT7JVkflXd01WNkjRdffOb3+Syyy7jmmuuYY899uCYY46ZlG9XdzqmkGRWkrXAvcDqqvpO\ns+mMJDckOTPJ7k3bAmD9uMPHmrannnNFkjVJ1mzcuLHL8iVpynrggQfYe++92WOPPbjtttu49tpr\nJ+W8nc4+qqrHgUOT7AVclOTfAB8EfgL8GrAKeD/w37fjnKua41i2bNnWrjwkaWRGPfvq+OOP5zOf\n+QwHHXQQBx54IEceeeSknHckU1Kr6v4kVwLHV9UnmubHkvw18L5mfQOwaNxhC5s2SdJT7L777lx6\n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\nAAAASUVORK5CYII=\n",
            "text/plain": [
              "<Figure size 432x288 with 1 Axes>"
            ]
          },
          "metadata": {
            "tags": []
          }
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "B9zocqA22q-F",
        "colab_type": "code",
        "outputId": "b89089a8-5c65-4d5a-ca66-e854c461e0c5",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 371
        }
      },
      "source": [
        "df4.hist(stacked = True, bins = 20)\n"
      ],
      "execution_count": 0,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "array([[<matplotlib.axes._subplots.AxesSubplot object at 0x7f2403099048>,\n",
              "        <matplotlib.axes._subplots.AxesSubplot object at 0x7f2402ff3a20>],\n",
              "       [<matplotlib.axes._subplots.AxesSubplot object at 0x7f2402fa6b70>,\n",
              "        <matplotlib.axes._subplots.AxesSubplot object at 0x7f2402fd7cc0>]],\n",
              "      dtype=object)"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 4
        },
        {
          "output_type": "display_data",
          "data": {
            "image/png": "iVBORw0KGgoAAAANSUhEUgAAAXcAAAEICAYAAACktLTqAAAABHNCSVQICAgIfAhkiAAAAAlwSFlz\nAAALEgAACxIB0t1+/AAAADh0RVh0U29mdHdhcmUAbWF0cGxvdGxpYiB2ZXJzaW9uMy4xLjIsIGh0\ndHA6Ly9tYXRwbG90bGliLm9yZy8li6FKAAAVhUlEQVR4nO3df5Ak5V3H8fdXEpPUEYN4uF6OSzYq\nxtKcoFmJmlguopEk6GGZQhADROKpBWrKU3P+KBN/UHX+gTFqEj0jcjE/AE0iV4GYpAhTsUQid4g5\nIEZPcid3uYDAhbBoaS18/WN6YJjs7M7u/OieZ9+vqq3t6emZ+V5v9+eefrr7mchMJEll+Yq6C5Ak\njZ7hLkkFMtwlqUCGuyQVyHCXpAIZ7pJUIMNdUqNExKGI+IG665h2hrskFchwl6QCGe4NFxE7I+I/\nIuLRiLgnIn607pqkCfjOans/HhF/GRHPrrugaWO4N99/AN8LPA/4beA9EbGp3pKksbsI+CHgG4Bv\nAn6z3nKmj+HecJn515n5+cx8IjOvA/4dOLPuuqQx+5PMvC8zHwauBC6su6BpY7g3XERcHBF3RsQX\nI+KLwEuAjXXXJY3ZfV3Th4Hn11XItHpG3QWov4h4IfDnwNnAP2bm4xFxJxD1ViaN3Zau6RcAn6+r\nkGlly73ZNgAJ/BdARLyedstdKt3lEXFqRJwM/AZwXd0FTRvDvcEy8x7gKuAfgfuBrcA/1FqUNBnv\nAz4G3Ev7ooLfq7ec6RN+WYcklceWuyQVyHCXpAIZ7pJUIMNdkgrUiOvcN27cmLOzs2t67WOPPcaG\nDRtGW9CIWeNorFTj/v37H8zMUyZY0poNs80Paxr+1mCdg1h2m8/M2n9e+tKX5lrdcssta37tpFjj\naKxUI7AvG7A9D/IzzDY/rGn4W2da5yCW2+btlpGkAhnuklQgw12SCtSIE6oazuzOG5ecf2jXayZc\niTQ6B44+wqVu22tmy12SCmS4S1KBDHdJKpB97pJq1e+c0Y6tEy6kMLbcJalAhrskFchwl6QCGe6S\nVCBPqDZIvxNL4E0bklbHcJ8SywW/JPWyW0aSCmS4S1KBDHdJKpDhLkkFMtwlqUBeLSNp6vgdBiuz\n5S4tISKujogHIuKurnknR8THI+Lfq99fXc2PiPijiDgYEZ+OiO+or3KpzXCXlnYNcE7PvJ3AzZl5\nGnBz9RjgVcBp1c924J0TqlHqy3CXlpCZnwQe7pm9DdhTTe8Bzuua/+5suw04KSI2TaZSaWn2uRfM\n4QxGbiYzj1XTXwBmqunNwH1dyx2p5h1DqonhLq1BZmZE5GpeExHbaXfbMDMzQ6vVGkdpK1pYWKjt\ns5eyY+vikvNnntP/uX7++L039H1u6+bnreq9BtW09dmxYrhHxNXAucADmfmSat7JwHXALHAIOD8z\nj0dEAG8DXg38N3BpZt4xntKlibs/IjZl5rGq2+WBav5RYEvXcqdW854mM3cDuwHm5uZyfn5+zOUu\nrdVqUddnL+XSvt/EtMhVB0bX/jx00fzI3qtb09ZnxyB97tfgiSUJYC9wSTV9CXBD1/yLq6tmvgt4\npKv7RqrFiv8tZuYnI2K2Z/Y2YL6a3gO0gDfRdWIJuC0iTuq0dEZVcAkc4bH5IuL9tLfxjRFxBHgz\nsAu4PiIuAw4D51eL30T7aPUg7SPW10+8YKnHWo95PLGkomXmhX2eOnuJZRO4fLwVNZ8n8Jtl6A6t\ntZxYgtGdXGrqyYxuvTWu9iTROPSus2lcj5L6W2u4D3ViCUZ3cqmpJzO69dbY7wTSJPWeXJrG9Sip\nv7XexOSJJUlqsEEuhfTEkiRNmUGulvHEkiRNGceWkaQCGe6SVCDHlpE0dt64N3m23CWpQIa7JBXI\ncJekAhnuklQgw12SCuTVMpJWxStfpoMtd0kqkOEuSQUy3CWpQPa5r1O9/aY7ti5y6c4b/cYcqRC2\n3CWpQLbcx6S7ZdxpFUvSpNhyl6QCGe6SVCC7ZSStC8vdfFXihQS23CWpQIa7JBXIcJekAtnnLq1S\nRBwCHgUeBxYzcy4iTgauA2aBQ8D5mXm8rholw11am7My88GuxzuBmzNzV0TsrB6/qZ7StFr9TrZO\n84lWu2Wk0dgG7Kmm9wDn1ViLNFzL3cPT8sa2Xm+Xi61RAh+LiAT+LDN3AzOZeax6/gvATO+LImI7\nsB1gZmaGVqs1oXKfbmFhYajP3rF1cXTFLGPmOZP7rH4GWU/Drs9xGUW3jIenWm9ekZlHI+JrgY9H\nxL92P5mZWQU/PfN3A7sB5ubmcn5+fiLF9mq1Wgzz2ZMaSmPH1kWuOlBvz/Ghi+ZXXGbY9Tku4+iW\n8fBURcvMo9XvB4APAWcC90fEJoDq9wP1VSgN33Jf0+EpjO4Qte5DokEOG5tweLmSQWqs+9Cz7r81\nQERsAL4iMx+tpl8J/A6wF7gE2FX9vqG+KqXhw31Nh6fVcyM5RK37kGiQQ9QmHF6uZJAaBzlEHae6\n/9aVGeBDEQHt/ed9mfl3EXE7cH1EXAYcBs6vscahlXYuaT0aKnG6D08j4mmHp5l5zMNTlSYz7wVO\nX2L+Q8DZk69IWtqa+9wjYkNEPLczTfvw9C6eOjwFD08lqRbDtNzXxeGpVDK7X8q15nD38FSSmss7\nVCWpQIa7JBWo2dfnSVKNpnk4DsN9AJ50kjRtDHcNbJpbMdJ6Y5+7JBXIcJekAhnuklQgw12SCmS4\nS1KBDHdJKpDhLkkFMtwlqUDexFTxLlRJJbHlLkkFsuWukeh35OOwBFI9DHdJWoNOg2bH1kUu7Wnc\nNKFRY7hLhes9qloqjFQe+9wlqUC23DVWDhMs1cNwlwrgpbzN0oQLDNZduLsTNIeteml8igx3A1zS\neje2cI+Ic4C3AScA78rMXeP6LKkJRrXNe0SjURhLuEfECcDbgR8EjgC3R8TezLxnHJ+n8iwVcDu2\nLjI/+VIGMqlt3qPSco26n35cLfczgYOZeS9ARFwLbANWvaGvtDF7za4aYmTbvMo1yf+cIzNH/6YR\nrwXOycw3VI9fB7wsM6/oWmY7sL16+GLgs2v8uI3Ag0OUOwnWOBor1fjCzDxlUsV0m/A2P6xp+FuD\ndQ6i7zZf2wnVzNwN7B72fSJiX2bOjaCksbHG0ZiGGpczqm1+WNOyHq1zOOO6Q/UosKXr8anVPKlU\nbvNqlHGF++3AaRHxooj4SuACYO+YPktqArd5NcpYumUyczEirgA+SvuysKsz8+5xfBYNOMwdgDWO\nRmNrnPA2P6zGrsce1jmEsZxQlSTVy1EhJalAhrskFWiqwz0iLoqIT0fEgYi4NSJOr7umXhFxTkR8\nNiIORsTOuuvpFhFbIuKWiLgnIu6OiF+su6Z+IuKEiPjniPhw3bVMq2nYXzqavN90NH3/meo+94j4\nHuAzmXk8Il4FvCUzX1Z3XR3VLen/Rtct6cCFTRmGISI2AZsy846IeC6wHzivKfV1i4hfAuaAr8rM\nc+uuZxo1fX/paPp+09H0/WeqW+6ZeWtmHq8e3kb72uImefKW9Mz8P6BzS3ojZOaxzLyjmn4U+Ayw\nud6qvlxEnAq8BnhX3bVMsynYXzoavd90NH3/mepw73EZ8JG6i+ixGbiv6/ERGvTH7xYRs8C3A5+q\nt5Il/SHwq8ATdRdSkCbuLx1Ts990NHH/KWI894g4i/bG+oq6a5lGEXEi8AHgjZn5pbrr6RYR5wIP\nZOb+iJivu54SuL+MVlP3n6lruUfE5RFxZ/Xz/Ij4NtqH69sy86G66+vR+FvSI+KZtDfM92bmB+uu\nZwkvB34kIg7RPjz//oh4T70lTY8p2186Gr/fdDR5/5n2E6ovAD4BXJyZt9ZdT6+IeAbtE0Nn0944\nbwd+oil3LkZEAHuAhzPzjXXXs5Kq5f7LnlBdm6bvLx1N3286mr7/THu3zG8BXwO8o72eWWzS6GxT\ncEv6y4HXAQci4s5q3q9n5k011qTxafT+0jEF+01Ho/efqW65rwcRsYX2V7d9L+1utPd3jxEuSUuZ\nuj739aS63vfDwGFglvYVA9fWWZOk6WDLvcEi4rtpDxu7KTMX665H0vSw5d5sW4DDBruk1TLcm+0+\n4AXV1QOSNDDDvdn+CTgG7IqIDRHx7Ih4ed1FSWo+w73BMvNx4IeBbwT+k/Zt2D9ea1GSpoInVCWp\nQLbcJalAhrskFchwl6QCGe6SVKBGXD+9cePGnJ2d7fv8Y489xoYNGyZX0BCsdTwGqXX//v0PZuYp\nEypJarQVwz0irgY6X5jwkmreW4CfBv6rWuzJkdAi4tdofxHA48AvZOZHV/qM2dlZ9u3b1/f5VqvF\n/Pz8Sm/TCNY6HoPUGhGHJ1ON1HyDdMtcA5yzxPy3ZuYZ1U8n2L8FuAD41uo176gGv5IkTdCK4Z6Z\nnwQeHvD9tgHXZub/ZubngIO0v+xWkjRBw/S5XxERFwP7gB3Vt6pvpv2t6h19v9g2IrYD2wFmZmZo\ntVp9P2hhYWHZ55vEWsdjmmqVmmCt4f5O4HeBrH5fBfzUat4gM3cDuwHm5uZyuf7U0vqGR212541L\nzj+06zXLvs71KpVrTZdCZub9mfl4Zj4B/DlPdb1MzRfbSlLJ1hTuEbGp6+GPAndV03uBCyLiWRHx\nIuA02iMbSpImaJBLId8PzAMbI+II8GZgPiLOoN0tcwj4GYDMvDsirgfuARaBy6uRDTWkfl0vkrSU\nFcM9My9cYvZfLLP8lcCVwxQlSRqOww9IUoEMd0kqkOEuSQUy3CWpQIa7JBXIcJekAhnuklQgw12S\nCmS4S1KBGvE1exqP5YYsWGnESEnTzZa7JBXIcJekAhnuklQg+9wbxGF9JY2KLXdJKpDhLkkFMtwl\nqUCGuyQVyHCXpAIZ7pJUIMNdkgq04nXuEXE1cC7wQGa+pJp3MnAdMAscAs7PzOMREcDbgFcD/w1c\nmpl3jKf06eX17JLGbZCW+zXAOT3zdgI3Z+ZpwM3VY4BXAadVP9uBd46mTEnSaqwY7pn5SeDhntnb\ngD3V9B7gvK75786224CTImLTqIqVJA1mrcMPzGTmsWr6C8BMNb0ZuK9ruSPVvGP0iIjttFv3zMzM\n0Gq1+n7YwsLCss83ySC17ti6OJliltFqtYpbr5KeMvTYMpmZEZFreN1uYDfA3Nxczs/P91221Wqx\n3PNNMkitlzagz/3QRfPFrVdJT1nr1TL3d7pbqt8PVPOPAlu6lju1midJmqC1hvte4JJq+hLghq75\nF0fbdwGPdHXfSJImZJBLId8PzAMbI+II8GZgF3B9RFwGHAbOrxa/ifZlkAdpXwr5+jHULElawYrh\nnpkX9nnq7CWWTeDyYYuSJA3HO1QlqUCGuyQVyHCXpAL5Harr1OzOG9mxdfHLrrk/tOs1NVUkaZRs\nuUtSgQx3SSqQ4S5JBTLcJalAhrskFchwl6QCGe6SVCDDXZIKZLhLUoG8Q3VMZhvwbUuS1i/DXU+z\n3H9KDk0gTQ+7ZSSpQIa7JBXIcJekAhnuklQgw12SCmS4S1KBhroUMiIOAY8CjwOLmTkXEScD1wGz\nwCHg/Mw8PlyZkqTVGEXL/azMPCMz56rHO4GbM/M04ObqsSRpgsZxE9M2YL6a3gO0gDeN4XMaofem\nn6W+l1SSJm3YlnsCH4uI/RGxvZo3k5nHqukvADNDfoYkaZUiM9f+4ojNmXk0Ir4W+Djw88DezDyp\na5njmfnVS7x2O7AdYGZm5qXXXntt389ZWFjgxBNPXHOd43Tg6CNPezzzHLj/f2oqZpVWW+vWzc8b\nXzErGGQbOOuss/Z3dQ9K69pQ4f60N4p4C7AA/DQwn5nHImIT0MrMFy/32rm5udy3b1/f51utFvPz\n8yOpc9SW6pa56sB0DNmz2lrrHFtmkG0gIgx3qbLmbpmI2BARz+1MA68E7gL2ApdUi10C3DBskZKk\n1RmmiTkDfCgiOu/zvsz8u4i4Hbg+Ii4DDgPnD1+mJGk11hzumXkvcPoS8x8Czh6mKEnScLxDVZIK\nZLhLUoEMd0kqkOEuSQUy3CWpQIa7JBXIcJekAhnuklQgw12SCmS4S1KBpmP4wpr1jvy4Xi23Huoc\nMVLSl7PlLkkFMtwlqUCGuyQVyHCXpAJ5QlUj0e9kqydapXrYcpekAhnuklQgw12SCmSfe8UblSSV\nxJa7JBXIcJekAo0t3CPinIj4bEQcjIid4/ocSdKXG0ufe0ScALwd+EHgCHB7ROzNzHvG8XlqLgcb\nk+oxrhOqZwIHM/NegIi4FtgGrDrcZ3feyI6ti1zaExLLBYMnR6fDav5OnW3A/xCkwURmjv5NI14L\nnJOZb6gevw54WWZe0bXMdmB79fDFwGeXecuNwIMjL3Q8rHU8Bqn1hZl5yiSKkZqutkshM3M3sHuQ\nZSNiX2bOjbmkkbDW8ZimWqUmGNcJ1aPAlq7Hp1bzJEkTMK5wvx04LSJeFBFfCVwA7B3TZ0mSeoyl\nWyYzFyPiCuCjwAnA1Zl59xBvOVD3TUNY63hMU61S7cZyQlWSVC/vUJWkAhnuklSgRoV7RMxHxCMR\ncWf181t9lntRRHyqGtrguuqk7aRrvSgiPh0RByLi1og4vc9y10TE57r+TWfUUOuyQ0FExLOq9Xiw\nWq+zk66xqmNLRNwSEfdExN0R8YtLLDPQNiKtd00c8vfvM/PcFZb5feCtmXltRPwpcBnwzvGX9jSf\nA74vM49HxKton/B7WZ9lfyUz/2ZypT1lwKEgLgOOZ+Y3RsQFtNfvj0++WhaBHZl5R0Q8F9gfER9f\nYtiKQbYRaV1rVMt9EBERwPcDnbDcA5w36Toy89bMPF49vI32tfxN9ORQEJn5f0BnKIhu22ivR2iv\n17Or9TxRmXksM++oph8FPgNsnnQdUgmaGO7fHRH/EhEfiYhvXeL5rwG+mJmL1eMj1B8AlwEfWeb5\nK6sunLdGxLMmVVRlM3Bf1+Ol1teTy1Tr9RHa67k2VdfQtwOfWuLplbYRad1rWrjfQXt8kNOBPwb+\ntuZ6VhQRZ9EO9zf1WeTXgG8GvhM4eZnlVImIE4EPAG/MzC/1PD1124hUh9rDPSIu75wcA07MzAWA\nzLwJeGZEbOx5yUPASRHROV8wsaENumuNiOdHxLcB7wK2ZeZDS72m6mrIzPxf4C9pd5NM0iBDQTy5\nTLVen0d7PU9cRDyTdrC/NzM/2Pt8Zn5pgG1EWvdqD/fMfHtmnpGZZwBPdPp6I+JM2vU91LN8ArcA\nr61mXQLcUEOtzwA+CLwuM/+t32siYlP1O2ifG7hrErV2GWQoiL201yO01+snsoa726p19BfAZzLz\nD/os83UrbSOSGnaHajVkwc/Rvmrif4Bfysxbq+duAt6QmZ+PiK+nfWLwZOCfgZ+sWsaTrPVdwI8B\nh6tZi51RC3tq/QRwChDAncDPdlqeE6z11cAf8tRQEFdGxO8A+zJzb0Q8G/gr2n3cDwMXdMbin3Cd\nrwD+HjgAPFHN/nXgBQCZ+afLbSOSntKocJckjUbt3TKSpNEz3CWpQIa7JBXIcJekAhnuklQgw12S\nCmS4S1KB/h9it3i2CZu4oQAAAABJRU5ErkJggg==\n",
            "text/plain": [
              "<Figure size 432x288 with 4 Axes>"
            ]
          },
          "metadata": {
            "tags": []
          }
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "OhHnTw3C2yy_",
        "colab_type": "code",
        "outputId": "59f31b6c-0b22-4c88-ef80-f9d643be3551",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 297
        }
      },
      "source": [
        "df4['a'].plot.hist(orientation = 'horizontal', cumulative = True)\n",
        "\n"
      ],
      "execution_count": 0,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "<matplotlib.axes._subplots.AxesSubplot at 0x7f2402e21438>"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 5
        },
        {
          "output_type": "display_data",
          "data": {
            "image/png": "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\n",
            "text/plain": [
              "<Figure size 432x288 with 1 Axes>"
            ]
          },
          "metadata": {
            "tags": []
          }
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "z5DcaB7e25Z-",
        "colab_type": "code",
        "outputId": "7eb35576-6921-4b94-817b-d9363c54b7db",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 283
        }
      },
      "source": [
        "df4['a'].diff().hist()"
      ],
      "execution_count": 0,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "<matplotlib.axes._subplots.AxesSubplot at 0x7f2402da9a58>"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 6
        },
        {
          "output_type": "display_data",
          "data": {
            "image/png": "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\n9L+XITsj8s2HkwAAAABJRU5ErkJggg==\n",
            "text/plain": [
              "<Figure size 432x288 with 1 Axes>"
            ]
          },
          "metadata": {
            "tags": []
          }
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "Wu6Hu-eQ290z",
        "colab_type": "code",
        "outputId": "34d6d136-c3cf-450c-b117-fd6a5dcbe8c7",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 371
        }
      },
      "source": [
        "\n",
        "df4[['a', 'b', 'c']].diff().hist(color='k', alpha=0.5, bins=30)"
      ],
      "execution_count": 0,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "array([[<matplotlib.axes._subplots.AxesSubplot object at 0x7f2402d54630>,\n",
              "        <matplotlib.axes._subplots.AxesSubplot object at 0x7f2401a60b00>],\n",
              "       [<matplotlib.axes._subplots.AxesSubplot object at 0x7f2401a1a0f0>,\n",
              "        <matplotlib.axes._subplots.AxesSubplot object at 0x7f2401a486a0>]],\n",
              "      dtype=object)"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 9
        },
        {
          "output_type": "display_data",
          "data": {
            "image/png": "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\n",
            "text/plain": [
              "<Figure size 432x288 with 4 Axes>"
            ]
          },
          "metadata": {
            "tags": []
          }
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "l48U_DCJ3KNF",
        "colab_type": "code",
        "outputId": "239adf81-8fa3-4f84-8cfa-ffc1b0c4871c",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 204
        }
      },
      "source": [
        "data = pd.Series(np.random.randn(1000))\n",
        "\n",
        "data = pd.DataFrame({'a' : np.random.randn(1000),\n",
        "                    'b': np.random.randint(0, 4, 1000) })\n",
        "data.head()"
      ],
      "execution_count": 0,
      "outputs": [
        {
          "output_type": "execute_result",
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
              "      <th>a</th>\n",
              "      <th>b</th>\n",
              "    </tr>\n",
              "  </thead>\n",
              "  <tbody>\n",
              "    <tr>\n",
              "      <th>0</th>\n",
              "      <td>-0.800721</td>\n",
              "      <td>3</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>1</th>\n",
              "      <td>0.845858</td>\n",
              "      <td>0</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>2</th>\n",
              "      <td>0.098642</td>\n",
              "      <td>1</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>3</th>\n",
              "      <td>-0.907384</td>\n",
              "      <td>2</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>4</th>\n",
              "      <td>-1.118213</td>\n",
              "      <td>1</td>\n",
              "    </tr>\n",
              "  </tbody>\n",
              "</table>\n",
              "</div>"
            ],
            "text/plain": [
              "          a  b\n",
              "0 -0.800721  3\n",
              "1  0.845858  0\n",
              "2  0.098642  1\n",
              "3 -0.907384  2\n",
              "4 -1.118213  1"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 10
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "MwL_Mm-u3BXY",
        "colab_type": "code",
        "outputId": "e4aeb618-ba54-4c3b-a92f-e526285a017e",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 370
        }
      },
      "source": [
        "data['a'].hist(by=data['b'], figsize=(6, 4))"
      ],
      "execution_count": 0,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "array([[<matplotlib.axes._subplots.AxesSubplot object at 0x7f24018d9ba8>,\n",
              "        <matplotlib.axes._subplots.AxesSubplot object at 0x7f2401909a20>],\n",
              "       [<matplotlib.axes._subplots.AxesSubplot object at 0x7f2401874fd0>,\n",
              "        <matplotlib.axes._subplots.AxesSubplot object at 0x7f24018305c0>]],\n",
              "      dtype=object)"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 11
        },
        {
          "output_type": "display_data",
          "data": {
            "image/png": "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\nAABJRU5ErkJggg==\n",
            "text/plain": [
              "<Figure size 432x288 with 4 Axes>"
            ]
          },
          "metadata": {
            "tags": []
          }
        }
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "FxWXzKO43PaP",
        "colab_type": "text"
      },
      "source": [
        "# scatterplot"
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "OArCORk03FEd",
        "colab_type": "code",
        "outputId": "09196a74-ae04-4c70-ff3c-f2720d3603c9",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 297
        }
      },
      "source": [
        "df4.plot.scatter(x = 'a', y = 'b', s = 50, grid = True)"
      ],
      "execution_count": 0,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "<matplotlib.axes._subplots.AxesSubplot at 0x7f240176d4a8>"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 13
        },
        {
          "output_type": "display_data",
          "data": {
            "image/png": "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\n",
            "text/plain": [
              "<Figure size 432x288 with 1 Axes>"
            ]
          },
          "metadata": {
            "tags": []
          }
        }
      ]
    },
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "DejFKo8F3fJQ",
        "colab_type": "text"
      },
      "source": [
        "# box plot"
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "2Aty33583Xg0",
        "colab_type": "code",
        "outputId": "8e6a2666-1340-4237-e01f-ca7c139985aa",
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 284
        }
      },
      "source": [
        "df4.plot.box()"
      ],
      "execution_count": 0,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "<matplotlib.axes._subplots.AxesSubplot at 0x7f24017770b8>"
            ]
          },
          "metadata": {
            "tags": []
          },
          "execution_count": 14
        },
        {
          "output_type": "display_data",
          "data": {
            "image/png": "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\niVtEJGb+H8DCrt45iSqSAAAAAElFTkSuQmCC\n",
            "text/plain": [
              "<Figure size 432x288 with 1 Axes>"
            ]
          },
          "metadata": {
            "tags": []
          }
        }
      ]
    },
    {
      "cell_type": "code",
      "metadata": {
        "id": "_VOXt4u43oVO",
        "colab_type": "code",
        "colab": {}
      },
      "source": [
        ""
      ],
      "execution_count": 0,
      "outputs": []
    }
  ]
}

## 추후에 할 것...
이젠 pandas를 이용하여 데이터 프레임을 다루는 것을 공부하게 될 것 같다.
무엇보다도 인공지능의 핵심은 데이터 전처리가 아닐까 싶다... 

열공하자ㅠ