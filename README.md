# relaycount-spamassassin
Spamassassin Plugin to score messages based on number of systems the email has been relayed through


## Site:
https://github.com/alasdairkeyes/relaycount-spamassassin


## Installation
- Copy the 30_relay_count.cf file into your SpamAssassin config folder
  (Usually /etc/mail/spamassassin/ or /etc/spamassassin/)
- Adjust the `blacklist_greater_than_or_equal` and
  `blacklist_less_than_or_equal` values if required
- Restart SpamAssassin


## Notes
- Plugin counts the number of public IPs that the message has been through
  on it's way to your mail server. If this value is too high or low, then
  it will obtain the given score
- This plugin was designed to score mail that is sent by being delivered
  directly to the mail server (by setting `blacklist_less_than_or_equal`
  to 1).
  Although not always, such mail is often spam which is being 
  sent by bypassing a standard SMTP server and connecting straight to.
  This is an attempt to filter mail that would normally be stopped by
  greylisting, but without the inconvenience of delayed messages
- Although I can't really see a use for the BLACKLIST_MAXIMUM_RELAY_COUNT
  check, it was trivial to add and there might be a use case for it
  `blacklist_greater_than_or_equal` in config set very high to stop it
  having any effect
  


## License
- See included license file - Released under this license to be as
  compatible with SpamAssassin as possible


## Dependencies
- Spamassassin


## Potential Issues
- Legitimate mail can trigger the these checks so only give them low scores
  so as not to filter HAM


## Future work
- Go on holiday


## Changelog
- 2016-11-05 :: 0.01    :: First release


## Author
- Alasdair Keyes - https://akeyes.co.uk/
