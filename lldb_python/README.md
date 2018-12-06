```
cat ~/.lldbinit
command script import /Users/mrchens/Documents/workSpace/funy/Loaction/ble_commands.py
command script add -f ble_commands.printworld hello
command script add -f ble_commands.bleBreak ble
command script add -f ble_commands.nsdata mydata

cat /Users/mrchens/Documents/workSpace/funy/Loaction/ble_commands.py

def printworld(debugger, command, result, internal_dict):
	print "world!"

def  nsdata(debugger, command, result, internal_dict):
	debugger.HandleCommand('br s -n \'[NSData(Extension) dataWithBase64String:]\'')
	debugger.HandleCommand('br s -n \'[NSData(Extension) md5String]\'')
	debugger.HandleCommand('br s -n \'[NSData(Extension) deflateValue2]\'')
	debugger.HandleCommand('br s -n \'[NSData(Extension) deflateValue]\'')
	debugger.HandleCommand('br s -n \'[NSData(Extension) inflateValue]\'')

	debugger.HandleCommand('br s -n \'[NSData(Common) dataWithReverse:]\'')
	debugger.HandleCommand('br s -n \'[NSData(Common) dataForHexString:]\'')
	debugger.HandleCommand('br s -n \'[NSData(Common) shakeHandCheck:]\'')
	debugger.HandleCommand('br s -n \'[NSData(Common) bytesFromUInt16:]\'')
	debugger.HandleCommand('br s -n \'[NSData(Common) uint16FromBytes:]\'')

	debugger.HandleCommand('br s -n \'[NSData(uniAttribute) setInAttributes:withName:]\'')

	debugger.HandleCommand('br s -n \'[NSData(AESAdditions) AES256DecryptWithKey:iv:]\'')
	debugger.HandleCommand('br s -n \'[NSData(AESAdditions) AES256EncryptWithKey:iv:]\'')

def bleBreak(debugger, command, result, internal_dict):

	# debugger.HandleCommand('br s -r \'\[BluetoothVC babyDelegate\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothVC locationcharacteristic\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothVC setLocationcharacteristic:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothVC socketcharacteristic\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothVC setSocketcharacteristic:\\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothVC socketdata\\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothVC setSocketdata:\\]$\'')

	debugger.HandleCommand('br s -r \'\[CBPeripheral initWithCentralManager:info:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral dealloc\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral description\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral sendMsg:args:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral sendMsg:requiresConnected:args:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral sendSyncMsg:args:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleMsg:args:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral attributeForHandle:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral setAttribute:forHandle:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral removeAttributeForHandle:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral invalidateAllAttributes\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleSuccessfulConnection:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleFailedConnection\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleDisconnection\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleConnectionStateUpdated:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral setOrphan\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral observeValueForKeyPath:ofObject:change:context:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral isConnected\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheral readRSSI\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheral discoverServices:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheral discoverIncludedServices:forService:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheral discoverCharacteristics:forService:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheral readValueForCharacteristic:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheral maximumWriteValueLengthForType:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral isReadyForUpdates\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheral writeValue:forCharacteristic:type:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral setBroadcastValue:forCharacteristic:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheral setNotifyValue:forCharacteristic:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheral discoverDescriptorsForCharacteristic:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheral readValueForDescriptor:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheral writeValue:forDescriptor:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral tag:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral untag:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral hasTag:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral getTimeSyncData\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheral openL2CAPChannel:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheral openL2CAPChannel:options:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral l2capChannelForPeer:withPsm:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral removeAllL2CAPChannels\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleNameUpdated:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleServicesChanged:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleRSSIUpdated:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleTimeSyncResponse:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleServicesDiscovered:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleL2CAPChannelOpened:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleL2CAPChannelClosed:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleAttributeEvent:args:attributeSelector:delegateSelector:delegateFlag:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleServiceEvent:serviceSelector:delegateSelector:delegateFlag:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleCharacteristicEvent:characteristicSelector:delegateSelector:delegateFlag:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleDescriptorEvent:descriptorSelector:delegateSelector:delegateFlag:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleServiceIncludedServicesDiscovered:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleServiceCharacteristicsDiscovered:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleCharacteristicValueUpdated:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleCharacteristicValueWritten:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleCharacteristicValueNotifying:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleCharacteristicDescriptorsDiscovered:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleDescriptorValueUpdated:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral handleDescriptorValueWritten:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral delegate\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral setDelegate:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral name\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral setName:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral RSSI\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral setRSSI:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral state\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral setState:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral services\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral setServices:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheral canSendWriteWithoutResponse\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheral setCanSendWriteWithoutResponse:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral writesPending\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral setWritesPending:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral isConnectedToSystem\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheral l2capChannels\]$\'')


	# debugger.HandleCommand('br s -r \'\[CBCentralManager peripheralWithIdentifier:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager peripheralWithInfo:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager peerWithInfo:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager forEachPeripheral:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager orphanPeripherals\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager dataArrayToUUIDArray:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager dealloc\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager observeValueForKeyPath:ofObject:change:context:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager init\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager initWithDelegate:queue:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager initWithDelegate:queue:options:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager retrievePeripherals:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager retrievePeripheralsWithIdentifiers:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager retrieveState\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager retrieveConnectedPeripherals\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager retrieveConnectedPeripheralsWithServices:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager retrieveConnectedPeripheralsWithServices:allowAll:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager scanForPeripheralsWithServices:options:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager stopScan\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager connectPeripheral:options:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager cancelPeripheralConnection:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager cancelPeripheralConnection:force:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager setDesiredConnectionLatency:forPeripheral:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager startTrackingPeripheral:options:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager stopTrackingPeripheral:options:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager enablePrivateModeForPeripheral:forDuration:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager handleRestoringState:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager handlePeripheralDiscovered:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager handlePeripheralConnectionCompleted:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager handlePeripheralDisconnectionCompleted:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager handlePeripheralConnectionStateUpdated:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager handlePeripheralTrackingUpdated:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager handleApplicationActivityEvent:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager handleAdvertisingAddressChanged:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager handleZoneLost:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager handleConnectionParametersUpdated:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager handleReadyForUpdates:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager isMsgAllowedWhenOff:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager isMsgAllowedAlways:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager handleMsg:args:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager delegate\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager setDelegate:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager isScanning\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager setIsScanning:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBCentralManager peripherals\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBCentralManager .cxx_destruct\]$\'')

	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager centralWithInfo:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager peerWithInfo:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager forEachCentral:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager dealloc\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager publishL2CAPChannelWithEncryption:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager publishL2CAPChannel:requiresEncryption:options:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager unpublishL2CAPChannel:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager l2capChannelForPeer:withPsm:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager removeAllL2CAPChannels\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager authorizationStatus\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager init\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager initWithDelegate:queue:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager initWithDelegate:queue:options:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager observeValueForKeyPath:ofObject:change:context:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager setDesiredConnectionLatency:forCentral:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager startAdvertising:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager stopAdvertising\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager addService:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager removeService:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager removeAllServices\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager respondToRequest:withResult:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager respondToTransaction:value:attributeID:result:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager updateValue:forCharacteristic:onSubscribedCentrals:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager supportsMultipleAdvertising\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager handleRestoringState:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager handleServiceAdded:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager handleGetAttributeValue:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager handleSetAttributeValues:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager handleNotificationAdded:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager handleNotificationRemoved:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager handleAdvertisingStarted:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager handleAdvertisingStopped:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager handleReadyForUpdates:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager handleSolicitedServicesFound:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager handleConnectionParametersUpdated:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager handleAdvertisingAddressChanged:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager handleL2CAPChannelOpened:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager handleL2CAPChannelClosed:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager handleL2CAPChannelPublished:\]$\'')
	# debugger.HandleCommand('br s -r \'\[CBPeripheralManager handleL2CAPChannelUnpublished:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager isMsgAllowedWhenOff:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager isMsgAllowedAlways:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager handleMsg:args:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager delegate\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager setDelegate:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager isAdvertising\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager setIsAdvertising:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager centrals\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager services\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager characteristicIDs\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager updateLock\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager readyForUpdates\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager waitingForReady\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager multipleAdvertisingSupported\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager setMultipleAdvertisingSupported:\]$\'')
	debugger.HandleCommand('br s -r \'\[CBPeripheralManager l2capChannels\]$\'')



	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew shared\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew init\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew writeuuidlocation:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew showPeripheralList\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew dismissPeripheralList\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew centralManagerDidUpdateState:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew centralManager:didDiscoverPeripheral:advertisementData:RSSI:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew stopScan\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew centralManager:didConnectPeripheral:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew alertView:clickedButtonAtIndex:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew peripheral:didDiscoverServices:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew centralManager:didFailToConnectPeripheral:error:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew peripheral:didDiscoverCharacteristicsForService:error:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew centralManager:didDisconnectPeripheral:error:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew peripheral:didUpdateValueForCharacteristic:error:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew peripheral:didUpdateNotificationStateForCharacteristic:error:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew peripheral:didWriteValueForCharacteristic:error:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew insertTableView:advertisementData:RSSI:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew tableView:numberOfRowsInSection:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew numberOfSectionsInTableView:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew tableView:titleForDeleteConfirmationButtonForRowAtIndexPath:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew tableView:canEditRowAtIndexPath:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew tableView:commitEditingStyle:forRowAtIndexPath:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew tableView:cellForRowAtIndexPath:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew tableView:heightForRowAtIndexPath:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew tableView:didSelectRowAtIndexPath:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew checkConnectState\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew cancleAll\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setPeripheral:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew connectState\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew backgroundView\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew peripheralTable\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew peripheralArray\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew newtimePeripheraArray\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew hadConnectDevices\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew nDevices\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew nServices\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew nCharacteristics\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew tipView\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew CBUUIDToString:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew peripheral\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew ConnectStateDidUpdate\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setConnectStateDidUpdate:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew characteristic\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setCharacteristic:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew socketcharacteristic\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setSocketcharacteristic:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew locationcharacteristic\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setLocationcharacteristic:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew socketData\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setSocketData:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setPeripheralArray:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setNewtimePeripheraArray:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew isConnect\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setIsConnect:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew isShowing\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setIsShowing:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew isConnectPeripheral\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setIsConnectPeripheral:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setBackgroundView:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setPeripheralTable:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setTipView:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew myConnectedPeripheral\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setMyConnectedPeripheral:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew manager\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setManager:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setNDevices:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setNServices:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setNCharacteristics:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setHadConnectDevices:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew socketdata\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setSocketdata:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew writeCharacteristic\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothManagerNew setWriteCharacteristic:\]$\'')
	# debugger.HandleCommand('br s -r \'\[BluetoothManagerNew .cxx_destruct\]$\'')

	# debugger.HandleCommand('br s -r \'\[BluetoothHelper shareHelper\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothHelper writeuuidsocket:andPerral:andCharacteristic:\]$\'')
	debugger.HandleCommand('br s -r \'\[BluetoothHelper writeuuidlocation:andPerral:andCharacteristic:\]$\'')

	# debugger.HandleCommand('br s -r \'\[MapPointVC viewWillAppear:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC viewWillDisappear:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC viewDidLoad\]$\'')
	debugger.HandleCommand('br s -r \'\[MapPointVC OTAUpdate:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC fakeBtnClickAction:\]$\'')
	debugger.HandleCommand('br s -r \'\[MapPointVC writeGPSToBle:\]$\'')
	debugger.HandleCommand('br s -r \'\[MapPointVC stopGps\]$\'')
	debugger.HandleCommand('br s -r \'\[MapPointVC delayMethod\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC rightNavBtnAction:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC leftNavBtnAction:\]$\'')
	debugger.HandleCommand('br s -r \'\[MapPointVC observeValueForKeyPath:ofObject:change:context:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC searchViewDidClickLocation:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC collectvcDidLocation:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC collectvcDidScan:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC didUpdateTXYUserLocation:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC receivedMapWillChanged:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC receivedMapDidChanged:\]$\'')
	debugger.HandleCommand('br s -r \'\[MapPointVC receivedMapGeo:\]$\'')
	debugger.HandleCommand('br s -r \'\[MapPointVC initializeData\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC creatNavBarUI\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC creatUI\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC AlphaLight:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC addCollect\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC isLocationOpen\]$\'')
	debugger.HandleCommand('br s -r \'\[MapPointVC backGPS\]$\'')
	debugger.HandleCommand('br s -r \'\[MapPointVC beginFake:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC upDown:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC traffic:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC tapMap:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC editCoord:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC heat:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC pano:\]$\'')
	debugger.HandleCommand('br s -r \'\[MapPointVC panoramaDidLoad:descreption:\]$\'')
	debugger.HandleCommand('br s -r \'\[MapPointVC panoramaLoadFailed:error:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC alertView:clickedButtonAtIndex:\]$\'')
	debugger.HandleCommand('br s -r \'\[MapPointVC otauPeripheralTest::\]$\'')
	debugger.HandleCommand('br s -r \'\[MapPointVC updata\]$\'')
	debugger.HandleCommand('br s -r \'\[MapPointVC isPureFloat:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC detailView\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC foldView\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC centerLocationImg\]$\'')
	debugger.HandleCommand('br s -r \'\[MapPointVC pointInfoView\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC fakeBtn\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC backBtn\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC searchView\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC locationService\]$\'')
	debugger.HandleCommand('br s -r \'\[MapPointVC inputGPS\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC tipView\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC bluetoothManager\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC setBluetoothManager:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC setCenterLocationImg:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC setPointInfoView:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC setFoldView:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC setDetailView:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC mapView\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC setMapView:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC setFakeBtn:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC mapType\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC setMapType:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC setLocationService:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC setBackBtn:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC setSearchView:\]$\'')
	debugger.HandleCommand('br s -r \'\[MapPointVC setInputGPS:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC setTipView:\]$\'')
	# debugger.HandleCommand('br s -r \'\[MapPointVC .cxx_destruct\]$\'')

	debugger.HandleCommand('br s -n \'[NSData(Extension) dataWithBase64String:]\'')
	debugger.HandleCommand('br s -n \'[NSData(Extension) md5String]\'')
	debugger.HandleCommand('br s -n \'[NSData(Extension) deflateValue2]\'')
	debugger.HandleCommand('br s -n \'[NSData(Extension) deflateValue]\'')
	debugger.HandleCommand('br s -n \'[NSData(Extension) inflateValue]\'')


	debugger.HandleCommand('br s -n \'[NSData(Common) dataWithReverse:]\'')
	debugger.HandleCommand('br s -n \'[NSData(Common) dataForHexString:]\'')
	debugger.HandleCommand('br s -n \'[NSData(Common) shakeHandCheck:]\'')
	debugger.HandleCommand('br s -n \'[NSData(Common) bytesFromUInt16:]\'')
	debugger.HandleCommand('br s -n \'[NSData(Common) uint16FromBytes:]\'')

	debugger.HandleCommand('br s -n \'[NSData(uniAttribute) setInAttributes:withName:]\'')

	# debugger.HandleCommand('br s -n \'[NSData(BLYJCE) dataByDECryptDESWithKey:error:]\'')
	# debugger.HandleCommand('br s -n \'[NSData(BLYJCE) dataByENCryptDESWithKey:error:]\'')
	# debugger.HandleCommand('br s -n \'[NSData(BLYJCE) dataByGZipDecompressingDataWithWindowSize:error:]\'')
	# debugger.HandleCommand('br s -n \'[NSData(BLYJCE) dataByGZipDecompressingDataWithError:]\'')
	# debugger.HandleCommand('br s -n \'[NSData(BLYJCE) dataByGZipCompressingAtLevel:windowSize:memoryLevel:strategy:error:]\'')
	# debugger.HandleCommand('br s -n \'[NSData(BLYJCE) dataByGZipCompressingWithError:]\'')

	debugger.HandleCommand('br s -n \'[NSData(AESAdditions) AES256DecryptWithKey:iv:]\'')
	debugger.HandleCommand('br s -n \'[NSData(AESAdditions) AES256EncryptWithKey:iv:]\'')
```





[lldb-python-office][lldb python reference]
[lldb-python-demo][lldb-python]
[lldb python reference]：http://lldb.llvm.org/python-reference.html?from=timeline&isappinstalled=0
[lldb-python]:https://github.com/SnowGirls/lldb-python