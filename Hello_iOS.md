# iOS技术交流
## How Do I Declare A Block in Objective-C?
## As a local variable:
returnType (^blockName)(parameterTypes) = ^returnType(parameters) {...};

## As a property:
@property (nonatomic, copy, nullability) returnType (^blockName)(parameterTypes);

## As a method parameter:
-(void)someMethodThatTakesABlock:(returnType (^nullability)(parameterTypes))blockName;

## As an argument to a method call:
[someObject someMethodThatTakesABlock:^returnType (parameters) {...}];

## As a parameter to a C function:
void SomeFunctionThatTakesABlock(returnType (^blockName)(parameterTypes));

## As a typedef:
- typedef returnType (^TypeName)(parameterTypes);
- TypeName blockName = ^returnType(parameters) {...};


This site is not intended to be an exhaustive list of all possible uses of blocks.
If you find yourself needing syntax not listed here, it is likely that a typedef would make your code more readable.

Unable to access this site due to the profanity in the URL? http://goshdarnblocksyntax.com is a more work-friendly mirror.
By Mike Lazer-Walker, who has a very bad memory for this sort of thing.
Like this site? Consider throwing me a few bucks via Ko-fi.
