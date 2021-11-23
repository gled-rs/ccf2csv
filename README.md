simple python3 script to convert a vcard export ( nextcloud or any other really ) file into a contact.csv file with number\tname format.

will also deduplicate name,tel contacts

Useful for SXMO users on pinephones.

# install:

git clone https://github.com/gled-rs/ccf2csv.git
pip install phonenumbers


# usage:
Name your contact file contacts.vcf and place it in the same directory as convert.py, then launch convert.py.

python convert.py

# tweaks:
3 variables at the beginning of the script can be used to tweak behavior

verbose_no_match=False
if True the script will print the vcard on the screen when it can't find a telephone number ( usually email only vcards )
 
insert_raw_tel=False
if True will insert whatever is found in the TEL section of the vcard, even if phonenumbers did not validated the format

try_to_fix_tel=True
if True will try to add + or +1 in front of the phone number in case your numbers were in a local US format.

