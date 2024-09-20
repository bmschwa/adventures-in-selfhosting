# Adventures in Self Hosting

First things first, lay out the apps

## Benefits and Challenges

One may ask a very reasonable question about all this: Why?  Why on earth would one spend the time, energy and money doing all this.   Why not just use the commonly used tools to accomplish these things?    This method for doing things demands a lot of attention and typically doesn't work as well as existing paid for solutions... so it demands a decent answer.

In bullet point form, I'd respond with... 

* I'm cheap.   I don't want to pay for third party services.

* I'm philosophically uneasy about delegating so much of my digital life to a for profit company.

* I'm disgusted by vendor lock in and the inability to leave platforms with my own work and data with ease.

* I think of it as a challenge ... something I *should* be able to do ... but *can* I?

* I think there's a business opportunity in self hosting.   I should be able to get it set up ... but then can turn it into a business?

## Subdomain summary

Even though wanting to make everything accessible through the local lan, it turned out  to be really tough (mDNS, no native support in synology, self-signed certificates, etc).   I ended up using a domain I own and setting records on a public DNS that point to the private IP of the synology device.

| Subdomain  | Service       | Notes |
| ---------- | ------------- | ----- |
| docs       | Paperless NGX |       |
| cloud      | Next Cloud    |       |
| pgadmin    | PG Admin      |       |
| photos     | Photo Prism   |       |
| accounting | Firefly III   |       |
| investing  | Ghostfolio    |       |

## Things to modify

Maybe it makes sense to have a  project for all the backend shit (postgres & redis)...

# Photos

# Documents

# Finance

## Spending & Saving

Using [Firefly-III](https://firefly-iii.org) in conjunction with the [Plaid Importer](https://github.com/dvankley/firefly-plaid-connector-2).

### Current Status

Its been surprisingly hard to get this all working. A Big part rests squarely on me: we have more accounts than necessary.

Some Notes of where I'm at.

- WellVetted Has a Production Account in Plaid. We need this to use the importer to get the activities. There is a cost (right now immaterial)

- I need to build a script to create .env files ... otherwise I need to store keys there... just don't feel great doing that, but in the interest of gettting shit done\

- When I run in WSL the line `make up language=python` seems to bring everything up correctly. *Does not work in windows*; you can run each component (front & back ends) seperately and that seems to be fine

- The Plaid Quick Start Connector is the only way I'm linking my banks now.   If we wanted to make this more professional - that'd need to change..... but the process for automating new accounts:
  
  - Get the plaid Quick start running in production
  
  - Connect to institution
  
  - Retrieve Item_Id, Access_Token
  
  - Modify the firelfy-plaid-connector-2 application file (`application.yml`) with a new entry for that bank.   (That file exists _on the nas_ ... and its white space sensitive)
  
  - 

## Investment Tracking

# Always more todo ...

Other miscellenous technology projects that complement this self hosting stuff, or just need to be written down somewhere and this is the best place I can think of now.

| Summary                                                                                                       | Notes & Descriptions                                                                                                                                                                             |
| ------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [Open Corporates](https://opencorporates.com/) plus [Sentence Piece](https://github.com/google/sentencepiece) | This would be a good learning opportunity for AI ... possibly commercial application?                                                                                                            |
| Oythereum Project!                                                                                            | Is this [BOB](https://www.gobob.xyz/) worthy?                                                                                                                                                    |
| Kodi Enhancements                                                                                             |                                                                                                                                                                                                  |
| Family Tree replacement                                                                                       | Haven't found a good self hosted option yet.                                                                                                                                                     |
| Caper Council Site                                                                                            | Been sitting on it for years.   Always wanted to have a respectable looking website.                                                                                                             |
| Sefaria on F-Droid.                                                                                           | [Sefaria Mobile App](https://github.com/Sefaria/Sefaria-Mobile) available on f-droid.   Two goals to accomplish: 1) philosophical 2) how does one get things published (and updated!) on sefaria |



## Misc Tech Projects

My [Bitcoin Dollar Cost Averager](https://github.com/bmschwa/kraken-nextcloud-accumulator) with Next Cloud Integration (on NAS)
