Use Case Name: Place Order

Actors:

* Registered Shopper \(Has an existing account, possibly with billing and shipping information\)
* Non-registered Shopper \(Does not have an existing account\)
* Fulfillment System \(processes orders for delivery to customers\)
* Billing System \(bills customers for orders that have been placed\)

Triggers:

* The user indicates that she wants to purchase items that she has selected.

Preconditions:

* User has selected the items to be purchased.

Post-conditions:

* The order will be placed in the system.
* The user will have a tracking ID for the order.
* The user will know the estimated delivery date for the order.

Normal Flow:

1. The user will indicate that she wants to order the items that have already been selected.
2. The system will present the billing and shipping information that the user previously stored.
3. The user will confirm that the existing billing and shipping information should be used for this order.
4. The system will present the amount that the order will cost, including applicable taxes and shipping charges.
5. The user will confirm that the order information is accurate.
6. The system will provide the user with a tracking ID for the order.
7. The system will submit the order to the
   _fulfillment system_
   for evaluation.
8. The
   _fulfillment system_
   will provide the system with an estimated delivery date.
9. The system will present the estimated delivery date to the user.
10. The user will indicate that the order should be placed.
11. The system will request that the
    _billing system_
    should charge the user for the order.
12. The
    _billing system_
    will confirm that the charge has been placed for the order.
13. The system will submit the order to the
    _fulfillment system_
    for processing.
14. The
    _fulfillment system_
    will confirm that the order is being processed.
15. The system will indicate to the user that the user has been charged for the order.
16. The system will indicate to the user that the order has been placed.
17. The user will exit the system.

Alternate Flows:

3A1: The user enters billing and shipping information for the order. The user desires to use shipping and billing information that differs from the information stored in her account. This alternate flow also applies if the user does not maintain billing and / or shipping information in their account, or if the user does not have an account.

1. The user will indicate that this order should use alternate billing or shipping information.
2. The user will enter billing and shipping information for this order.
3. The system will validate the billing and shipping information.
4. The use case continues

5A1: The user will discover an error in the billing or shipping information associated with their account, and will change it.

1. The user will indicate that the billing and shipping information is incorrect.
2. The user will edit the billing and shipping information associated with their account.
3. The system will validate the billing and shipping information.
4. The use case returns to step 2 and continues.

5A2: The user will discover an error in the billing or shipping information that is uniquely being used for this order, and will change it.

1. The user will indicate that the billing and shipping information is incorrect.
2. The user will edit the billing and shipping information for this order.
3. The use case returns to step 3A1 step 3.

10A1: The user will determine that the order is not acceptable \(perhaps due to disatisfaction with the estimated delivery date\) and will cancel the order.

1. The user will request that the order be cancelled.
2. The system will confirm that the order has been cancelled.
3. The use case ends.



