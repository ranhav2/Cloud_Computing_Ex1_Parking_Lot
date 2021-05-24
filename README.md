# Cloud Computing Ex1 - Parking Lot
Helen Grein and Ran Havaletzki

 a system that would track and compute cars entry & exit from parking lots, as well as compute their charge.
 
## The scenario

- A cloud-based system to manage a parking lot.
- Camera will recognize license plate and ping cloud service
- Actions:
    • Entry (record time, license plate and parking lot)
    • Exit (return the charge for the time in the parking lot)
- Price – 10$ per hour (by 15 minutes)

## Endpoints
two HTTP endpoints:
- POST /entry?plate=123-123-123&parkingLot=382
 - Returns ticket id
- POST /exit?ticketId=1234
 - Returns the license plate, total parked time, the parking lot id and the charge (based on 15 minutes increments).
The charge for parking is 10$ per hour.

## Installation

```sh
# Download and unzip the 'Cloud_Computing_Ex1_Parking_Lot.zip' file
# setup AWS CLI
sudo apt install awscli zip
# Configure AWS setup (keys, region, etc)
aws configure
# setup the parking lot.
./setup.sh
# After recieving two http endpoints
# For car entrance:
curl "http://[Entry HTTP endpoint]/?plate=???-???-???&parkingLot=???"
# For car exit:
curl "http://[Exit HTTP endpoint]/?ticketId=?...?"
```
