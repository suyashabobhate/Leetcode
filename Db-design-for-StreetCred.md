

DbdesignforStreetCred

TherearetwocollectionsnamelyUsersandWatchlists.

UndertheUserscollection,inasingleUserIddocumenttherearecommonﬁelds:

birth\_year (number)

name (map)

● first\_name (string)

● last\_name (string)

watchlists (map)

● owned (array)

➤ 0 (string)

● subscribed (array)

➤ 0 (string)

andanother\_user\_infosubcollectioninwhichasingledocumentscontainsthefollowingﬁelds

address (map)

● city (string)

● country (string)

● street (string)

● zipcode (number)

annual\_income (string)

citizenship\_status (string)

country\_of\_birth (string)

dob (string)

email\_id (string)

employer\_info (map)

● employer\_address (string)

● employer\_name (string)

● job\_title (string)

employment\_status (string)

funding (string)

investible\_or\_liquid\_assets (string)

net\_worth (string)





phone\_number (number)

visa\_details (map)

● country\_of\_citizenship (string)

● expiration\_date (string)

● visa\_type (string)

UndertheWatchlistscollection,inasingleWatchlistIddocumenttherearecommon

ﬁelds:

isDefault (boolean)

isDeleted (boolean)

isForked (boolean)

isPublished (boolean)

name (string)

stocks\_list (map)

● 0 (string)

● 1 (string)

● 2 (string)

user\_id (string)

andasubcollectioncalledhistorywhichincludesthehistoryofactionsmadebytheownero f

watchlists.

Thehistorysubcollectioncontainsthefollowing:

data (array)

● 0 (map)

➤ action (string)

➤ date/time (timestamp)

➤ description (array)

■ 0 (map)

➤ name (string)

➤ price (number)





Standardcases

● Userlogsin

● Userscancreate,update,delete,andreadtheirownedwatchlists

● Subscriberscaneitheronlyreadthesubwatchlistoriftheyeditthewatchlistthenthesaid

watchlistwillbechangedfromsubscribedwatchlisttoownedwatchlist.

● Userscanshareownedwatchlistswithotherusers.

● Watchlistshaveahistoryfeaturewhichshowstheactionsrelatedtowatchlistmadebythe

owner.

EdgeCases

● Whentheuserdeletesownedwatchlistbutthesubscriberisstillsubscribedandiswatching

thesamewatchlist.

● Whentheuserupdatesownedwatchlistwhilethesubscriberisreadingitatthesametime.

● Ifthewatchlistsshouldbedownloadableoravailableoﬄine.

● Iftheuseraddsthewatchlistwhilethestockdetailsarebeingupdated.

● Iftheuserdeletestheiraccountthenthewatchlistssubscribedfromthatusermustbeeither

deletedorchangedfromsubscribedtoownedforthesubscribersofthatuser.

● Amountofwatchliststobeshown.

● Timezoneanddaylightsaving.





RiskMitigation

● Usersmustnotbeallowedtoupdateanythingrelatedtopayment.

● Usersmustnotbeallowedtomanipulatethenumberofforks,watchlistsandsubscribers.

● Usersmustnotbeunsubscribedbeforeconﬁrmingsoafterclickingonunsubscribebutton.

● Subscribersmustnotbeabletoreadwatchlistsnotsubscribedorownedbythemselves.

![alt text](https://viewer.diagrams.net/?tags=%7B%7D&highlight=0000ff&edit=_blank&layers=1&nav=1&title=StreetcredTriggers.drawio#R7Vzbcts2EP0azbQP8vAiUtJjLk46TTOTqSdN8giRkISEIlQQsqx8fXElCV5s2qIIqu1LIi5BENqzZ7G7WHniv9k9vCdgv%2F2IY5hMPCd%2BmPhvJ57nzpch%2B49LTkoS%2Bo6UbAiKlawQ3KGfUAn1sAOKYWYMpBgnFO1NYYTTFEbUkAFC8NEctsaJ%2BdY92MCa4C4CSV36BcV0K6WLwCnkv0G02eo3u466swN6sBJkWxDjY0nk3078NwRjKj%2FtHt7AhGtP60U%2B967lbr4wAlPa5YFTcut%2B%2FZx%2B%2BT195%2Fw1c2ebu3cfpu5cLY6e9DeGMVOAusSEbvEGpyC5LaSvCT6kMeTTOuyqGPMHxnsmdJnwO6T0pNAEB4qZaEt3iboLHxD9Wvr8jU91E6irtw9qZnFx0hcpJaev5YvSU%2FyyeExc6efqalKay%2FCBRPAR3XjK3ADZQPrIOF%2BO43orvUCB8B7iHWTrYQMITABF96ZhAWWfm3xcASH7oFB8BqLewiaiBYrfSneuDdHZqBD13f8RPRfRYFyIev8jei6i4bgQndlF1HsJpAWK3wwQrW2kve%2Bk4tFXhIBTacAeo5RmpZk%2FcQEboKLWpQrYdMg6r8RVTwxfBo8On7qPjmcf5HoLW8y%2F%2BBnmGVyNeZ5tZj1bTw3AuYmfHzrmDNLM1UMVt9IDlOpb3oPkoL7B5wwSJknwJuMPpzWoj1tE4d0eCO0dWaJmwtSq8XtIKHx4VJfq7qJi09rGj0XK5Oo8aFtKl6q6680fu1aj4BflNVPnxnFm5jY7c%2BZPeGVx9QkSxPTGzOBcDvkdXfViXLtvGyciAgGFnBZHQKNtgjLp%2BAemhxeMjh%2FLq%2BSHF1T44S2H5cesIz%2BWo%2BLHrI0f2WGVRQStBEUYWl4Idtz801W2F3pyMN2KkaPiT15Ts8afvKh3PfwZLIMLOnJEO8GRkMSzmpT%2FSyB1%2B4b0RRnczAkMf6Fj9LacrDbeTPkuk5MFbU4ZxoiOLmTx%2FQFd7vdX3yEThx%2F%2BdML9z78T8PNjMrWTwrZQbd6NaxUeNGJSJlXjF%2Ff6oFCDzZsAz%2BYV4KRTqOWxz%2Bai1%2FyeVi5WxgdLv1cuNqrYvZrtvLtdPenUQzt2deH6SNjmVmOYwBHmgrOZ9VjWcnFwiNrgvGMA03sN8Sxk5i22XMvSijoHiCKGDLVg2NUaoG2zXtSUd0xyVcViZWKSFRSawkQIAVdijKPDDgqvxsupDsuB%2BXg%2BWvRr8HaTJIERRTgVE7Fv6DkH6WcQnwav%2BT%2FHVGbZenIxGeLPgwSnm%2BJRnWXHkAKU2HBLuRtS8E27xnt5Lat3AJc1ANFawDDdH1bMfW%2BFTpnm0kL5EeAX2WEl8eKqCRO20tcrTpsN%2F8RuxhpN1GoHSM0jOKVCHlTMrV5XMhSBuF5FyTqsI9m52OgGF9th%2FGsJr4ZPrTU6T%2BfW4%2BpK0euu0pM7vYJf2UTms1xknQn5Ue1TTJhdjAhW2wT6IELHxPdFTGhIiJsHjqubR6%2B7yoS8uD5SOvjBgHRoTrtrirNBj0ZjeqEJdz0fkiZszWLrB0JAPKVtk6URPHrJKtERiOMiONoiHiyd8pCIBz36XjVU1oE1MGKmwRkQVhgw70iAagmjPyDqReA8ds1VH21BuuHq5wd0pf11ylckdRtFMOP6JXzN%2FMOG2VCqH5FTrjGZ6FQmPuwTFOk8qDlOZmMqCzFsQMwsMyoJsEpl5MsE2jL%2FaZqbreWHmCWjgB6qZkbgPZa35Zox%2B1qIMVq%2F8BcZaDCp9qmytlNKBwpB5zeI2X9tXG5h6uVJDCWKaYppGSKm9kVm0DR3kYesCd7l43f4vlCzxlwu1shAUDn5sZl2VLnlhh3JlRcOet9erjDYunGchRlwLeZntAD1sql54VVsal698iv8hPR42i390J0Ozg8I9%2BXbOkqzHpd1rghfbFvy2xuqRH2FhwlSdYgL95BkWPpnlK5xo5sjMKME5VEF1tMgUQaLmLKArI7xCWoFzsExmVa6PDt3nFwMk9Byh%2FmYG8zD5sbxLr8iONdlVQ7BLn%2Fo1bjTXeFvvm58d162DrO9z9JWFzb0vzYqfG5zpwtb3XNxxmnhHKjaEG%2BtU8T9j7jKfky%2BoberWauXcZXBwL%2BfCOspt0yrRCKmM63VKU%2Brho89QjP2CLoe4FysTufVVKYLnPGkdBYGMwHsEaR0YhyaqqS8SHUJ1PltkfTq%2BNtZI5iIlHptJLv1U1GTsp2AqaHQgFXnQD0YMlBvBMZqF%2F%2FzOzee67AusvV2bDvzho3g6q0eJa%2Bk2LFSxdas4I0kWaOjGpodi7F5LdfOqXPLwdmTsW13ijzdxWSpta%2BlZbQ2UThvsZWByNZQdjeOrfURRdbQagVSY89r7P8wqsS6Em2ZnrWoouth%2BAs2L3ZZ%2FF0bCVrx54H8238A)