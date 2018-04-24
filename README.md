# ZipLine mPay Mobile Payment Interface Version 1.47

	Revision History: 

	Version	Date	Author(s)	Summary of changes
	1.00	08/23/2013	Ted Zuccarelli	Initial version
	
	1.01	08/23/2013	Jim Killeen	Review revise section 4, 5
	
	1.02	08/30/2013	Jim Killeen	Revise section 4
	
	1.03	09/01/2013	Jim Killeen	Added GetStoreAddress method
	
	1.04	09/27/2013	Jim Killeen	Added GetAuthToken method, modified ActivateStorePumpRequest and MPayStoreLocation objects
	
	1.05	10/04/2013	Ted Zuccarelli	Cleanup for generic use
	
	1.06	10/15/2013	Jim Killeen	Added description for GetAuthToken
	
	1.07	10/22/2013	Jim Killeen	Added GetTransactionResult and GetAllStores methods
	
	1.08	10/31/2013	Jim Killeen	Removed SessionID from AutoActivateResponse
	
	1.09	11/11/2013	Jim Killeen	Added sections  for PayByCard and PayByToken
	
	1.10	11/26/2013	Jim Killeen	Added missing GetAllStoresResponse object
	
	1.11	12/02/2013	Jim Killeen	Changed StoreID from int to uint, Added SalesInfo to Payment methods.
	
	1.12	12/03/2013	Jim Killeen	Added GetTransactionResults method
	
	1.13	12/06/2013	Jim Killeen	Added section 4.5 for Sample request/response messages
	
	1.14	12/06/2013	Jim Killeen	Added PreAuthByToken method
	
	1.15	12/07/2013	Jim Killeen	Added AuthCode to Transaction object, modified input parameters for GetTransactionResult(s) methods.
	
	1.16	12/09/2013	Jim Killeen	Added Error Codes section
	
	1.17	01/12/2014	Jim Killeen	Added properties CurrencyType, UnitsOfMeasure, SessionID, and TransactionID to FuelTransactionDetail and InsideStoreTransactionDetail objects Added PayReversalByToken method
	
	1.18	01/29/2014	Jim Killeen	Added section 5 Sequence Diagrams for various mPay implementations
	
	1.19	01/30/2014	Jim Killeen	Added SessionID property to TransactionResult object. Removed SessionID property from FuelTransactionDetail and InsideStoreTransactionDetail objects.
	
	1.20	02/06/2014	Jim Killeen	Added authentication type description to section 4.1
	
	1.21	02/18/2014	Jim Killeen	Corrected some typos
	
	1.22	03/07/2014	Jim Killeen	Added NpcApprovalCode to FuelTransactionDetail and InsideStoreTransactionDetail objects
	
	1.23	05/09/2014	Jim Killeen	Added method GetTransactionReport
	
	1.24	06/03/2014	Jim Killeen	Added ConsumerLocation object to input parameters for GetAuthToken method, added IsStoreIDSetByGPS property to Store object for ActivateStorePump method.
	
	1.25	06/12/2014	Jim Killeen	Added GPSTimestamp property to ConsumerLocation object
	
	1.26	07/30/2014	Jim Killeen	Added methods GetTransactionResultEx, GetTransactionResultsEx, and GetTransactionReportEx. These methods support multiple sales items per transaction result. For example, a single transaction result may contain fuel and car wash sales items.
	
	1.27	09/08/2014	Jim Killeen	Added StoreCode to handle alpha numeric store numbers. StoreCode has been added to the MPayStoreLocation object which is returned on the FindStores, GetStoreAddress, and GetAllStores methods. StoreCode can be provided on several methods input parameters.
	
	1.28	04/08/2015	Jim Killeen	Added enumeration PosType to MPayStoreLocation object. Added methods GetTransactionReceipt and GetTransactionReceipts to return the POS data receipts.
	
	1.29	06/09/2015	Jim Killeen	Added methods to support Credit Card processing.
	
	1.31	06/23/2015	Jim Killeen	Added CancelCardTransaction method
	
	1.32	06/25/2105	Jim Killeen	Added GetCreditCardRegistrationPageToken method. Update error messages.
	
	1.33	07/02/2015	Jim Killeen	Added UserID to GetCreditCardRegistrationResultsResponse object
	
	1.34	07/06/2015	Jim Killeen	Added SessionID and Token to CancelCardTransactionRequest object
	
	1.35	07/26/2015	Jim Killeen	Added GetCreditCardVaultMerchants method. Modified GetAuthToken to return User’s registered merchantID. Removed MerchantID from GetCreditCardRegistrationPageTokenRequest  object.
	
	1.36	03/16/2016	Jim Killeen	Added section 5.4 mPay4 sequence diagrams which illustrate the mPay interface to the Conexxus Mobile Service.
	
	1.37	05/26/2016	Jim Killeen	Added StoreDescription field to MPayStoreLocation, TransactionDetail objects. The store description will now be returned on the following methods: GetStoreAddress, FindStores, GetAllStores, GetTransactionResult, GetTransactionResults, GetTransactionReport, GetTransactionResultsEx, GetTransactionReportEx
	
	1.38	07/28/2016	Jim Killeen	Added LastTransID field to GetTransactionReportRequest object to allow iterating over a result set.
	
	1.39	10/27/2016	Jim Killeen	Added SiteAuthorizationType to the Customer input request object of the GetAuthToken method
	
	1.40	11/01/2016	Jim Killeen	Added POSType to TransactionDetail object. Added Token to TransactionResult and TransactionResultEx objects.
	
	1.41	03/01/2017	John Knupp	Updated to include details on GetUserToken and GetTransactionToken
	
	1.42	07/19/2017	Jim Killeen	Added two new properties for GetAuthToken’s  request. The full length pseudo CardNumber or customer’s loyalty customer card number can be returned upon request.
	
	1.43	08/22/2017	Jim Killeen	Added optional TipAmount property to Transaction object to store transaction tip amounts.
	
	1.44	09/04/2017	Jim Killeen	Added three new methods: RegisterPaymentType(), GetPaymentToken(), and SetPaymentAuthAmount()
	
	1.45	09/07/2017	John Knupp	Modify response error message to return message text, message code or both to the caller
	
	1.46	11/03/2017	Jim Killeen	Added two new properties for GetAuthToken and GetTransactionToken request. The full length pseudo CardNumber or customer’s loyalty customer card number can be returned upon request. Added new eStorePosType entries for NCR stores.
	
	1.47	12/04/2017	Jim Killeen	Added NetSpend support to Above Site Auth (ASA) processing for ActivateStorePump and PayByToken methods.
